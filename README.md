# elixirChatter : basic project on elixir

to create a new pheonix server :
-------------------------------
mix phx.new <project_name>

the chatter folder has been created.
follow the readme of that folder and come back here.

psql guide - https://chartio.com/resources/tutorials/how-to-list-databases-and-tables-in-postgresql-using-psql/

mix ecto.gen.migration add_table : to add new table
write in the new migration file

and run : mix ecto.migrate


create model for the database table:
------------------------------------
define schema and changeset in new folder in lib. (here it is in schemas->chatter_box.ex)

so far there is nothing in the table we have just defined the schema.

we can query the database by using ecto. : lib->chatter_queries.ex
(but as there is nothing till now, nothing to query)


to put the rows in the tables in database. 
-----------------------------------------
seed.exs need to send data.
it will send data by repo.insert query which is in chatter_queries.ex->create_chat.
create_chat validates the input with the changeset.

to run seeds.exs : mix run priv/repo/seeds.exs

![GitHub Logo](/images/seed_image.png)


to fetch data
-----------------------------------------

1. create a route in router (/get/:status)
2. create a controller and add the functions u will be calling too
    (chatter_controller/get)
3. use render function that has a template (here, getting_message.html)
4. for that template , we need to create template folder chatter(based      on controller name) and
     make a file getting_message.html.eex 
     ( elixir strictly follows name convention)
    ![GitHub Logo](/images/naming_convention.png)

4. create a chatter_view.ex (follow the naming convention)

