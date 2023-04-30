# FINAL-PROJECT-

import turtle

screen = turtle.Screen()
screen.setup(500,500)

bob = turtle.Turtle()
screen.addshape("classroom.gif")
bob.shape("classroom.gif")

dictionary = {
    1: {
        '1st grade environmental science:Which bin would you recycle a water bottole in? a) plastic b) paper c) aluminum d) glass': 'a',
        '1st grade biology:How many major oceans are there on Earth? a) 3 b) 4 c) 5 d) 6': 'c'
    },
    2: {
        '2nd grade ecology:Fill in the blank. Soil is the ______ for many animals. a) Food b) Home c) Atmosphere d) Resource': 'b',
        '2nd grade earth science: The following is not a layer of the Earth? a) Atmosphere b) Crust  c) Mantle d) Core': 'a'
    },
    3: {
        '3rd grade chemistry:Two properties of matter are volume and ______ a) Property b) Matter c) Mass d) Electricity': 'c',
        '3rd grade astronomy, Which planet is closest to the Sun? a) Mars b) Venus  c) Uranus d) Mercury': 'd'
    },
    4: {
        '4th grade physics: On which surface would a ball move slowly because of friction? a) Wood b) Title c) Marble floor d) Carpet': 'd',
        '4th grade zoology: What is the sequence of the life cycle stages of metamorphosis? a) wake up, eat, sleep, deathb) egg, pupa, larva, adult c) egg, larva, pupa, adult d) born, hungry, sleeping, death': 'c'
    },
    5: {
        '5th grade computer science:Name the part that sends signals to other parts of the computer and tells it what to do. A) CPU B) Motherboard C) Icon D)Hard Drive': 'a'
    }
}
list1 = []
while 1:
    if len(list1) == 4:
        break
    grade = int(input("Enter grade category (1-4): "))
    the_same = False
    for j in range(len(list1)):
        if grade== list1[j]:
            the_same = True
    if the_same == True:
        continue
    list1.append(grade)
    if grade not in dictionary:
        print("Invalid grade category!")
    else:
        for i, question in enumerate(dictionary[grade]):
            answer_key = str(grade) + str(i+1)
            user_answer = input(question)
            if True == print('Congratulation you won $1000'):
                pass
            print(user_answer == dictionary[grade][question])
