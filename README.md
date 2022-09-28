# Interview
follow up question

here is my solution and test cases and the output

#meetings=[[0,30],[15,20],[5,10]]  output:2
#meetings=[[0,10],[10,20],[20,30]] output:2
#meetings=[[0,30],[0,30],[0,30]]  output:3

def countpeople(meetings):
    meetings.sort()
    dq=deque()
    count=0

    refer=meetings.pop(0)


    while dq or count==0:
        if count>0:
            meetings=list(dq)
            refer=meetings.pop(0)
            dq=deque()

        for meeting in meetings:
            if meeting[0]<=refer[1]:
                dq.append(meeting)
            else:
                refer=meeting

        count+=1

    return count

print(countpeople(meetings))
