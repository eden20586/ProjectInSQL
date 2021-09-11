from tkinter import *
from tkinter import messagebox
import mysql.connector
from tkinter import ttk
mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  #hidden code
    password="RyTmH451" ,
  database = "customize cars to customer"
)

print(mydb)

mycursor = mydb.cursor()

window = Tk()
window.geometry('1920x1080')
window.title("Welcome to Eden's app")

tree = ttk.Treeview(window, column=("c1", "c2", "c3" , "c4" , "c5" , "c6"), show='headings' , height = '8')
tree.column("#1", anchor = CENTER , width = "90")
tree.heading("#1", text="Car name")
tree.column("#2", anchor = CENTER , width = "80")
tree.heading("#2", text="Car price")
tree.column("#3", anchor = CENTER , width = "80")
tree.heading("#3", text="Car year")
tree.column("#4", anchor = CENTER , width = "80")
tree.heading("#4", text="Finish level")
tree.column("#5", anchor = CENTER , width = "150")
tree.heading("#5", text="Intercity fuel consumption")
tree.column("#6", anchor = CENTER , width = "140")
tree.heading("#6", text="Urban fuel consumption")
tree.grid(row = 7 , column = 0)


tree_two = ttk.Treeview(window, column=("c1", "c2" , "c3" , "c4" , "c5"), show='headings' , height = '8')
tree_two.column("#1", anchor = CENTER , width = "80")
tree_two.heading("#1", text="License name")
tree_two.column("#2", anchor = CENTER , width = "160")
tree_two.heading("#2", text="License address")
tree_two.column("#3", anchor = CENTER , width = "115")
tree_two.heading("#3", text="License activity area")
tree_two.column("#4", anchor = CENTER , width = "115")
tree_two.heading("#4", text="License activity time")
tree_two.column("#5", anchor = CENTER , width = "75")
tree_two.heading("#5", text="License from")
tree_two.grid(row = 7 , column = 3)

tree_three = ttk.Treeview(window, column=("c1", "c2", "c3" , "c4" , "c5" , "c6" ), show='headings' , height = '6')
tree_three.column("#1", anchor = CENTER , width = "80")
tree_three.heading("#1", text="Car name")
tree_three.column("#2", anchor = CENTER , width = "80")
tree_three.heading("#2", text="Car price")
tree_three.column("#3", anchor = CENTER , width = "80")
tree_three.heading("#3", text="Car year")
tree_three.column("#4", anchor = CENTER , width = "80")
tree_three.heading("#4", text="Finish level")
tree_three.column("#5", anchor = CENTER , width = "150")
tree_three.heading("#5", text="Intercity fuel consumption")
tree_three.column("#6", anchor = CENTER , width = "140")
tree_three.heading("#6", text="Urban fuel consumption")
tree_three.grid(row = 14 , column = 0)

tree_four = ttk.Treeview(window, column=("c1", "c2", "c3"), show='headings' , height = '6')
tree_four.column("#1", anchor = CENTER , width = "80")
tree_four.heading("#1", text="Count cars")
tree_four.column("#2", anchor = CENTER , width = "110")
tree_four.heading("#2", text="Car name")
tree_four.column("#3", anchor = CENTER , width = "80")
tree_four.heading("#3", text="Car year")
tree_four.grid(row = 14 , column = 3)

lbl = Label(window, text="" , fg ='black' , font=("Arial Bold", 12 ))
lbl.grid(column=0, row=6)

lbl = Label(window, text="Enter your id : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=0)

lbl = Label(window, text="Enter your max budget : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=1) 

lbl = Label(window, text="Enter your status : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=2)

lbl = Label(window, text="Enter your age : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=3)

lbl = Label(window, text="Enter your position in work : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=4)

lbl = Label(window, text="Enter manufacturer name that you recive  : " , font=("Arial Bold", 12))
lbl.grid(column=3, row=1)

lbl = Label(window, text="Enter your living area : " , font=("Arial Bold", 12))
lbl.grid(column=3, row=2)

lbl = Label(window, text="")
lbl.grid(column=0, row=8)

lbl = Label(window, text="")
lbl.grid(column=0, row=12)

lbl = Label(window, text="")
lbl.grid(column=0, row=14)

lbl = Label(window, text="Enter your max budget : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=9)

lbl = Label(window, text="Enter car year  : " , font=("Arial Bold", 12))
lbl.grid(column=0, row=10)

lbl = Label(window, text="Click on the button and get a list of chosen cars in all history " , font=("Arial Bold", 12))
lbl.grid(column=3, row=9)

txt_customer_id = Entry(window,width=10)
txt_customer_id.grid(column=1,row=0)

txt_max_budget = Entry(window,width=10)
txt_max_budget.grid(column=1,row=1)

txt_status = Entry(window,width=10)
txt_status.grid(column = 1 , row = 2)

txt_age = Entry(window,width=10)
txt_age.grid(column = 1 , row = 3)

txt_position_in_work = Entry(window,width=10)
txt_position_in_work.grid(column = 1 , row = 4)

txt_manufacturer_name = Entry(window,width=10)
txt_manufacturer_name.grid(column = 4 , row = 1)

txt_living_area = Entry(window,width=10)
txt_living_area.grid(column = 4 , row = 2 )

txt_max_budget_third_query = Entry(window,width=10)
txt_max_budget_third_query.grid(column=1,row=9)

txt_car_year = Entry(window,width=10)
txt_car_year.grid(column=1,row=10)

def get_car_name(): 
      #mycursor.execute("SELECT cars_models.model_name FROM cars_models INNER JOIN customers_and_cars_model ON cars_models.chassis_num = customers_and_cars_model.chassis_num INNER JOIN customers ON customers.id  WHERE age = %s" , [txt_age.get()])
      mycursor.execute("SELECT cars_models.model_name , cars_models.price , cars_models.year , cars_models.finish_level , cars_models.Intercity_fuel_consumption , cars_models.urban_fuel_consumption FROM cars_models JOIN customers_and_cars_model ON cars_models.chassis_num = customers_and_cars_model.chassis_num JOIN customers ON customers.id  WHERE cars_models.price <=%s AND customers.status = %s AND customers.age = %s AND customers.position_in_work =%s AND customers_and_cars_model.customer_id =%s  "  , [txt_max_budget.get() , txt_status.get() , txt_age.get() , txt_position_in_work.get() , txt_customer_id.get()])
      result = mycursor.fetchall()
      if result is not None and len(result) > 0 :
          for row in result:
            print(row)
            tree.insert("", END , values = row)
      else:
            messagebox.showinfo('System message','No cars found')

      #mycursor.execute("SELECT customers.living_area , customers.id FROM customers WHERE customers.id = %s" , [txt_id.get()])
def get_license_garages(): 
      mycursor.execute("SELECT DISTINCT licensed_garages.garage_name‏ , licensed_garages.garage_address‏ , licensed_garages.activity_area , licensed_garages.garage_activity_time , licensed_garages.license_from  FROM licensed_garages WHERE  licensed_garages.license_from  =%s AND licensed_garages.activity_area =%s"  , [txt_manufacturer_name.get() , txt_living_area.get()])
      result_two = mycursor.fetchall()
      if result_two is not None and len(result_two) > 0 :
        for row in result_two:
            print(row)
            tree_two.insert("", END , values = row)
      else:
            messagebox.showinfo('System message','No license garages found')
def show_cars(): 
        mycursor.execute("SELECT cars_models.model_name , cars_models.price , cars_models.year , cars_models.finish_level , cars_models.Intercity_fuel_consumption , cars_models.urban_fuel_consumption FROM cars_models WHERE cars_models.year = %s AND price <= %s" , [txt_car_year.get() , txt_max_budget_third_query.get()])
        result_three = mycursor.fetchall()
        if result_three is not None and len(result_three) > 0 :
         for row in result_three:
            print(row)
            tree_three.insert("", END , values = row)
        else:
            messagebox.showinfo('System message','No cars found')
def show_chosen_cars(): 
        mycursor.execute("SELECT count(model_name) , model_name , year FROM cars_models JOIN customers_and_cars_model ON cars_models.chassis_num = customers_and_cars_model.chassis_num GROUP BY model_name")
        result_four = mycursor.fetchall()
        if result_four is not None and len(result_four) > 0 :
         for row in result_four:
            print(row)
            tree_four.insert("", END , values = row)

btn = Button(window, text="Get a car by profile ", command=get_car_name , bg='orange', fg='black')
btn.grid(column= 0, row= 6)

btn = Button(window, text=" Get a license garage ", command=get_license_garages , bg='orange', fg='black')
btn.grid(column=3, row=4)

btn = Button(window, text="Get a car by year ", command=show_cars , bg='orange', fg='black')
btn.grid(column= 0, row= 12)

btn = Button(window, text="Show chosen cars ", command=show_chosen_cars , bg='orange', fg='black')
btn.grid(column= 3, row= 11)








window.mainloop()
