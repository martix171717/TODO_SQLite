Module 13

Task: SQLite in practice

In app.py:

1. to create a table and insert sample todos:

if __name__ == "__main__":
     
    create_todos_sql = """
    -- todos table
    CREATE TABLE IF NOT EXISTS todos (
    id integer PRIMARY KEY,
    title VARCHAR(50) NOT NULL,
    description text NOT NULL,
    if_done BOOLEAN DEFAULT FALSE NOT NULL
     );
    """

    db_file = "todos.db"
    
    conn = todos.create_connection(db_file)
    if conn is not None:
        todos.execute_sql(conn, create_todos_sql)

    todo_1=("Trening", "Boxing Girls", False)

    todo_2=("Zakupy", "Cola zero, popcorn", True)

    todo_3=("Prezenty", "Perfumy dla mamy", False)

    todo1_id =todos.add_todo(conn, todo_1)
    todo2_id = todos.add_todo(conn, todo_2)
    todo3_id = todos.add_todo(conn, todo_3)
    
    #s1 = todos.select_all(conn, "todos")
    #print(s1)
    #s2= todos.select_where(conn, "todos", if_done=False)
    #print(s2)
    #conn.commit()
    
    #todos.update(conn, "todos", 2, description="Cola zero, popcorn i chipsy")
    
    #todos.delete_where(conn, "todos", id=3)
    #todos.delete_all(conn, "todos")
    
    conn.close()
    
2. to select all todos and to select these todos where if_done is False:

if __name__ == "__main__":
     
    create_todos_sql = """
    -- todos table
    CREATE TABLE IF NOT EXISTS todos (
    id integer PRIMARY KEY,
    title VARCHAR(50) NOT NULL,
    description text NOT NULL,
    if_done BOOLEAN DEFAULT FALSE NOT NULL
     );
    """

    db_file = "todos.db"
    
    conn = todos.create_connection(db_file)
    #if conn is not None:
        #todos.execute_sql(conn, create_todos_sql)

    todo_1=("Trening", "Boxing Girls", False)

    todo_2=("Zakupy", "Cola zero, popcorn", True)

    todo_3=("Prezenty", "Perfumy dla mamy", False)

    #todo1_id =todos.add_todo(conn, todo_1)
    #todo2_id = todos.add_todo(conn, todo_2)
    #todo3_id = todos.add_todo(conn, todo_3)
    
    s1 = todos.select_all(conn, "todos")
    print(s1)
    s2= todos.select_where(conn, "todos", if_done=False)
    print(s2)
    conn.commit()
    
    #todos.update(conn, "todos", 2, description="Cola zero, popcorn i chipsy")
    
    #todos.delete_where(conn, "todos", id=3)
    #todos.delete_all(conn, "todos")
    
    conn.close()
    
3. To update todos:

if __name__ == "__main__":
     
    create_todos_sql = """
    -- todos table
    CREATE TABLE IF NOT EXISTS todos (
    id integer PRIMARY KEY,
    title VARCHAR(50) NOT NULL,
    description text NOT NULL,
    if_done BOOLEAN DEFAULT FALSE NOT NULL
     );
    """

    db_file = "todos.db"
    
    conn = todos.create_connection(db_file)
    #if conn is not None:
        #todos.execute_sql(conn, create_todos_sql)

    todo_1=("Trening", "Boxing Girls", False)

    todo_2=("Zakupy", "Cola zero, popcorn", True)

    todo_3=("Prezenty", "Perfumy dla mamy", False)

    #todo1_id =todos.add_todo(conn, todo_1)
    #todo2_id = todos.add_todo(conn, todo_2)
    #todo3_id = todos.add_todo(conn, todo_3)
    
    #s1 = todos.select_all(conn, "todos")
    #print(s1)
    #s2= todos.select_where(conn, "todos", if_done=False)
    #print(s2)
    #conn.commit()
    
    todos.update(conn, "todos", 2, description="Cola zero, popcorn i chipsy")
    
    #todos.delete_where(conn, "todos", id=3)
    #todos.delete_all(conn, "todos")
    
    conn.close()
    
4. To delete all todos or to delete this todo where id=3:

if __name__ == "__main__":
     
    create_todos_sql = """
    -- todos table
    CREATE TABLE IF NOT EXISTS todos (
    id integer PRIMARY KEY,
    title VARCHAR(50) NOT NULL,
    description text NOT NULL,
    if_done BOOLEAN DEFAULT FALSE NOT NULL
     );
    """
    
    db_file = "todos.db"
    
    conn = todos.create_connection(db_file)
    #if conn is not None:
        #todos.execute_sql(conn, create_todos_sql)

    todo_1=("Trening", "Boxing Girls", False)

    todo_2=("Zakupy", "Cola zero, popcorn", True)

    todo_3=("Prezenty", "Perfumy dla mamy", False)

    #todo1_id =todos.add_todo(conn, todo_1)
    #todo2_id = todos.add_todo(conn, todo_2)
    #todo3_id = todos.add_todo(conn, todo_3)
    
    #s1 = todos.select_all(conn, "todos")
    #print(s1)
    #s2= todos.select_where(conn, "todos", if_done=False)
    #print(s2)
    #conn.commit()
    
    #todos.update(conn, "todos", 2, description="Cola zero, popcorn i chipsy")

    todos.delete_where(conn, "todos", id=3)
    todos.delete_all(conn, "todos")
    conn.close()
