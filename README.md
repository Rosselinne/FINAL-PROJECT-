from data import dictionary, awards, finalRound
from data import validateInput, isValidAnswer, fifthGraderAnswer

def playGame():
    
    list1 = []
    total_award = [0]

    while len(list1) < 4:
        grade = input("Enter grade category (1-4): ")
        if not validateInput(["1","2", "3", "4"], grade):
            print("Invalid input. Enter a valid choice\n")
            continue

        grade = int(grade)
        if grade in list1:
            print("You have already selected this grade category!")
            continue

        list1.append(grade)
       
        
        if grade not in dictionary:
            print("Invalid grade category!")
            
        else:
            for i, question in enumerate(dictionary[grade]):
                answer_key = str(grade) + str(i+1)
                response = "\n Or Enter save for a chance to be saved by a 5th grader.\nYour answer: "
                user_answer = input(question + response)
                correctAnswer = dictionary[grade][question]

                while not validateInput(["a","b","c", "d", "save"],user_answer):
                    user_answer = input("Please enter choices a, b, c, d or save: ")

                if(user_answer == "save"):
                    randomAnswer = fifthGraderAnswer()
                    failMessage = "NOT SAVED! Fifth grader answered: " + randomAnswer + ". Correct Answer is: " + correctAnswer
                    if isValidAnswer(randomAnswer, correctAnswer, "SAVED!" , failMessage):
                        total_award[0] += awards[grade]

                else:
                    failMessage = "WRONG! Correct Answer is: " + correctAnswer
                    if isValidAnswer(user_answer, correctAnswer, "CORRECT!", failMessage):
                        total_award[0] += awards[grade]
                print("Total award: " + str(total_award[0]) + "\n")
 
    print("Total award: " + str(total_award[0]) + "\n")


    finalRound(total_award)







playGame()
