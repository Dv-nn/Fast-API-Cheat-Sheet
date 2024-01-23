# Fast API Cheat Sheet  
FastAPI — это современный, быстрый (высокопроизводительный) веб-фреймворк для создания API, в основе которого лежит стандартная аннотация типов Python.

> pip install fastapi[all]   --установить FastAPI
> pip install "uvicorn[standard]"   --установить uvicorn для работы в качестве сервера    

Самый простой FastAPI файл    
> from fastapi import FastAPI  
>
> app = FastAPI()
>
> @app.get("/")
> async def root():
>    return {"message": "Hello World"}

> uvicorn main:app --reload     --запустить сервер


 
 
____  
[Документация](https://fastapi.netlify.app/ru/)
