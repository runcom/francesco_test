# AD CODE 1
f = open('inputAC1.txt')
input1 = f.read()
in1 = input1.split(', ')
compass = ['E', 'N', 'W', 'S']
orientation = 1
distance_x = 0
distance_y = 0
right = ['R']
list_input = len(in1)
positions = [[0 for x in range(2)] for y in range(list_input)]
steps_list = []
j = 0
z = 0
temporary_x = 0
temporary_y = 0
for i in in1:
    result = 0
    direction = [i[0]]
    print '---------------------------------------------'
    print 'NEW DIRECTION: '
    print
    print 'Turn ', direction

    if direction == right:
        orientation -= 1
        if orientation == -5:
            orientation = -1
    else:
        orientation += 1
        if orientation == 4:
            orientation = 0

    direction2 = [i[1:]]
    print 'It''s necessary to go: ', compass[orientation], ' for ', int(''.join(direction2)), ' steps'
    print
    if compass[orientation] == compass[0]:
        temporary_x = distance_x
        print 'temporary x is: ', temporary_x
        distance_x += int(''.join(direction2))
        print 'distance x is: ', distance_x
        positions[j][0] = distance_x
        positions[j][1] = distance_y
        if distance_x < 0 < temporary_x:
            print 'case 1'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x == 0 and distance_x < 0 and temporary_x > distance_x:
            print 'case 1.1'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x > 0 and distance_x == 0 and temporary_x > distance_x:
            print 'case 1.2'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x < 0 < distance_x:
            print 'case 2'
            result = range(temporary_x, distance_x + 1)
        elif distance_x < temporary_x < 0:
            print 'case 3'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x < distance_x < 0:
            print 'case 4'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x > distance_x > 0:
            print 'case 5'
            result = range(temporary_x, distance_x + 1, -1)
        else:
            print 'default case'
            result = range(temporary_x, distance_x + 1)
        print 'new vector is: ', result
        length_results = len(result)
        new = [distance_y] * length_results
        c = 0
        for r in result[1:]:
            steps_list.append([result[c], new[c]])
            c += 1
        print '---------------------------------------------'
        print 'NEW POSITION:'
        print 'Direction: East'
        print
        print 'Position on x axis is:', positions[j][0]
        print 'Position on y axis is:', positions[j][1]
        print '---------------------------------------------'
        print '---------------------------------------------'
        print
        print
    elif compass[orientation] == compass[1]:
        temporary_y = distance_y
        print 'temporary y is: ', temporary_y
        distance_y += int(''.join(direction2))
        print 'distance y is: ', distance_y
        positions[j][0] = distance_x
        positions[j][1] = distance_y
        if distance_y <= 0 <= temporary_y:
            print 'caso 1'
            if temporary_y == 0 and distance_y < 0:
                print 'caso 1.1'
                result = range(temporary_y, distance_y - 1, -1)
            elif temporary_y > 0 and distance_y == 0:
                print 'caso 1.2'
                result = range(temporary_y, distance_y - 1, -1)
            else:
                result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y < 0 < distance_y:
            print 'caso 2'
            result = range(temporary_y, distance_y + 1)
        elif distance_y < temporary_y < 0:
            print 'caso 3'
            result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y < distance_y < 0:
            print 'caso 4'
            result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y > distance_y > 0:
            print 'caso 5'
            result = range(temporary_y, distance_y + 1, -1)
        else:
            print 'caso default'
            result = range(temporary_y, distance_y + 1)
        print 'new vector is: ', result
        length_results = len(result)
        new = [distance_x] * length_results
        c = 0
        for r in result[1:]:
            steps_list.append([new[c], result[c]])
            c += 1
        print '---------------------------------------------'
        print 'NEW POSITION:'
        print 'Direction: North'
        print
        print 'Position on x axis is:', positions[j][0]
        print 'Position on y axis is:', positions[j][1]
        print '---------------------------------------------'
        print '---------------------------------------------'
        print
        print
    elif compass[orientation] == compass[2]:
        temporary_x = distance_x
        print 'temporary x is: ', temporary_x
        distance_x -= int(''.join(direction2))
        print 'distance x is: ', distance_x
        positions[j][0] = distance_x
        positions[j][1] = distance_y
        if distance_x < 0 < temporary_x:
            print 'case 1'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x == 0 and distance_x < 0 and temporary_x > distance_x:
            print 'case 1.1'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x > 0 and distance_x == 0 and temporary_x > distance_x:
            print 'case 1.2'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x < 0 < distance_x:
            print 'case 2'
            result = range(temporary_x, distance_x + 1)
        elif distance_x < temporary_x < 0:
            print 'case 3'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x < distance_x < 0:
            print 'case 4'
            result = range(temporary_x, distance_x - 1, -1)
        elif temporary_x > distance_x > 0:
            print 'case 5'
            result = range(temporary_x, distance_x + 1, -1)
        else:
            print 'default case'
            result = range(temporary_x, distance_x + 1)
        print 'new vector is: ', result
        length_results = len(result)
        new = [distance_y] * length_results
        c = 0
        for r in result[1:]:
            steps_list.append([result[c], new[c]])
            c += 1
        print '---------------------------------------------'
        print 'NEW POSITION:'
        print 'Direction: West'
        print
        print 'Position on x axis is:', positions[j][0]
        print 'Position on y axis is:', positions[j][1]
        print '---------------------------------------------'
        print '---------------------------------------------'
        print
        print
    elif compass[orientation] == compass[3]:
        temporary_y = distance_y
        print 'temporary y is: ', temporary_y
        distance_y -= int(''.join(direction2))
        print 'distance y is: ', distance_y
        positions[j][0] = distance_x
        positions[j][1] = distance_y
        if distance_y <= 0 <= temporary_y:
            print 'caso 1'
            if temporary_y == 0 and distance_y < 0:
                print 'caso 1.1'
                result = range(temporary_y, distance_y - 1, -1)
            elif temporary_y > 0 and distance_y == 0:
                print 'caso 1.2'
                result = range(temporary_y, distance_y - 1, -1)
            else:
                result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y < 0 < distance_y:
            print 'caso 2'
            result = range(temporary_y, distance_y + 1)
        elif distance_y < temporary_y < 0:
            print 'caso 3'
            result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y < distance_y < 0:
            print 'caso 4'
            result = range(temporary_y, distance_y - 1, -1)
        elif temporary_y > distance_y > 0:
            print 'caso 5'
            result = range(temporary_y, distance_y + 1, -1)
        else:
            print 'caso default'
            result = range(temporary_y, distance_y + 1)
        print 'new vector is: ', result
        length_results = len(result)
        new = [distance_x] * length_results
        c = 0
        for r in result[1:]:
            steps_list.append([new[c], result[c]])
            c += 1
        print '---------------------------------------------'
        print 'NEW POSITION:'
        print 'Direction: South'
        print
        print 'Position on x axis is:', positions[j][0]
        print 'Position on y axis is:', positions[j][1]
        print '---------------------------------------------'
        print '---------------------------------------------'
        print
        print
    j += 1
print '---------------------------------------------'
print 'Final position on x axis is ', distance_x
print 'Final position on y axis is ', distance_y
print
print 'The solution for advent of code is: ', (abs(distance_x) + abs(distance_y))
print '---------------------------------------------'
print
print 'The list of positions in the x,y reference frame is:'
print
print positions

print
print steps_list
t = 0
for s in steps_list:
    temp = steps_list[0:t]
    l = 0
    for m in temp:
        if steps_list[t] == temp[l]:
            print
            print 'The position at index', t, 'had been met at index', l
            print 'The position visited twice is:'
            print 'Position x is:', steps_list[t][0]
            print 'Position y is:', steps_list[t][1]
            print
            print 'The solution for advent of code is: ', (abs(steps_list[t][0]) + abs(steps_list[t][1]))
            print '------------------------------------------------'
        l += 1
    t += 1
