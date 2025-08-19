from tkinter import*
from pytube import YouTube       #pip install pytube
from tkinter import filedialog 
from tkinter import PhotoImage
from tkinter import messagebox
  

R=Tk()
R.title("DOWNLOAD WINDOW")
R.geometry('800x450')
img=PhotoImage(file="youtube.png")     #take any img and save it
bg=Label(R,image=img)
bg.place(relheight=1,relwidth=1)
u=Label(R,text='Download youtube video',font=('helvetica', 30),fg="red").place(x=200,y=200)
l1=Label(R,text='Enter utube url',font=('helvetica', 15)).place(x=300,y=300)
E1=Entry(R)
E1.place(x=300,y=350)

Folder_Name = ""

#file location
def locationError():
    global Folder_Name
    Folder_Name = filedialog.askdirectory()
    print("Folder_Name",Folder_Name)
    if str(Folder_Name) =='':
        messagebox.showinfo("Info","Select path")
    else:
        messagebox.showinfo("Info","Selected")


def download():
    ytd_url = E1.get()
    try:
        obj = YouTube(ytd_url)
        filter = obj.streams.filter(progressive=True,file_extension='mp4')
        filter.get_highest_resolution().download(Folder_Name,filename='video.mp4')
        Label(R, text= "Downloading Started",font=('helvetica', 10)).place(x=300,y=450)
    except Exception as e:
        Label(R, text= "Downloading Failed",font=('helvetica')).place(x=300,y=450)
    
l2 = Label(R,text="Save the Video File",font=("jost",15,"bold")).place(x=300,y=500)

E2 = Button(R,width=10,bg="green",fg="white",text="Choose Path",command=locationError)
E2.place(x=300,y=550)

Button(text='Download', command=download, bg='brown', fg='white', font=('helvetica', 9, 'bold')).place(x=300,y=400)
R.mainloop()
