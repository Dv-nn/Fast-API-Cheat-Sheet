# Fast API Cheat Sheet  
FastAPI — это современный, быстрый (высокопроизводительный) веб-фреймворк для создания API, в основе которого лежит стандартная аннотация типов Python.

> pip install fastapi[all]  
> pip install pony
> pip install bit  
> pip install pyTelegramBotAPI  


> import fastapi    
>
> api = fastapi.FastAPI()  
>
> @api.get('/hello')  
> def api_hello():  
>    return {"hello":'from api!'}  

Запускается сервер с API через терминал    
> uvicorn main:api --reload    

 
