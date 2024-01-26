# Fast API Cheat Sheet  
____  
FastAPI — это современный, быстрый (высокопроизводительный) веб-фреймворк для создания API, в основе которого лежит стандартная аннотация типов Python.

> pip install fastapi[all]          #установить FastAPI  
> pip install "uvicorn[standard]"   #установить uvicorn для работы в качестве сервера      

*Самый простой FastAPI файл*        
> from fastapi import FastAPI    
>  
> app = FastAPI()  
>  
> @app.get("/")  
> async def root():  
>    return {"message": "Hello World"}  

> uvicorn main:app --reload        #запустить сервер  
____  
*Обработка различных переменных в пути*  
В fastapi мы можем обрабатывать как статичные пути, так и пути с переменными, причем при обработке запросов - этим переменным в пути мы можем сразу объявлять тип данных. 

> @api.get('/user/{nick}')      # переменные в пути заключаются в фигурные скобки  
> def get_nick(nick):           # в функцию передаем эту переменную и работаем с ней дальше  
>   return {"user":nick}        # при запросе страницы вернет строку, которую мы вписали после последнего слеша  

> @api.get('/userid/{id:int}')  # мы можем задавать тип данных прямо в пути через двоеточие  
> def get_id(id):                  
>    return {"user":id}     


Чтобы начать принимать и обрабатывать различные параметры, в функцию обработки запроса FastAPI мы должны добавить аргументы  
> @api.get("/users/")  
> def get_users(skip: int = 0, limit: int = 10):  
>    return fake_database['users'][skip: skip + limit]

*POST, PUT, DELETE и другие запросы*    
> @api.get('/')       # метод для обработки get запросов  
> @api.post('/')      # метод для обработки post запросов  
> @api.put('/')       # метод для обработки put запросов  
> @api.delete('/')    # метод для обработки delete запросов  
> def index(request: Request):  # тут request - будет объектом в котором хранится вся информация о запросе  
>    return {"Request" : [request.method,    # тут наш API вернет клиенту метод, с которым этот запрос был совершен  
>                         request.headers]}  # а тут в ответ вернутся все хедеры клиентского запроса

____  
[Документация](https://fastapi.netlify.app/ru/)
