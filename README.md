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
 
____  
[Документация](https://fastapi.netlify.app/ru/)
