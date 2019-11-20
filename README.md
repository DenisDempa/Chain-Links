# Chain-Links
My first small python program in GUI for calculating number of chain links nedded when installing new chain on bicycle.

from tkinter import *

window=Tk()

window.wm_title("Chain Links")

def chain_length():
    num_of_links= int(int(chainstay_value.get()) * 0.157 + int(chainring_value.get())/2 +
    int(cassete_value.get())/2 + 2)
    if num_of_links % 2 != 0:
        num_of_links += 1
    links.insert(END, num_of_links)


Label(window, text="Chainstay Length (in mm):").grid(row=0)
chainstay_value=StringVar()
chainstay=Entry(window, textvariable=chainstay_value)
chainstay.grid(row=0,column=2)

Label(window, text="Chainring (T):").grid(row=1)
chainring_value=StringVar()
chainring=Entry(window, textvariable=chainring_value)
chainring.grid(row=1,column=2)

Label(window, text="Cassete (1st gear T):").grid(row=2)
cassete_value=StringVar()
cassete=Entry(window, textvariable=cassete_value)
cassete.grid(row=2,column=2)

b1=Button(window, text="Confirm", command=chain_length)
b1.grid(row=3,column=2)

b2=Button(window, text="Close", command=window.destroy)
b2.grid(row=6, column=2)

Label(window, text="Number of chain links:").grid(row=5)
links=Text(window,height=0,width=20)
links.grid(row=5,column=2)

window.mainloop()
