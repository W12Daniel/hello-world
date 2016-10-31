# hello-world
from Tkinter import*
from math import*

def move():
	global x,y,dx,dy,flag
	x=x+dx
	y=y+dy
	if x>=360:
		x,dx,dy=360,0,+15
	if y>=360:
		y,dx,dy=360,-15,0
	if x<=10 and y>=360:
		x,dx,dy=10,0,-15
	if x<=10 and y<=10:
			y,dx,dy=10,15,0
	can1.coords(oval2,x+30,y+30,x-30,y-30)
	if flag>0:
		abl1.after(50,move)
def start():
	global flag
	if flag==0:
		flag=1
		move()

	
	
	
x,y,dx,dy,flag=10,10,15,0,0
abl1=Tk()
can1=Canvas(abl1,bg="dark grey",height=400,width=400)
can1.pack()
oval2=can1.create_oval(x-30,y-30,x+30,y+30,fill="red")
but2=Button(abl1,text="start",command=start).pack()
but3=Button(abl1,text="quit",command=abl1.destroy).pack()
abl1.mainloop()