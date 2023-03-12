https://jinja.palletsprojects.com/en/3.0.x/api/ - документация Environment
file_loader = FileSystemLoader("templates")
env = Environment(loader=file_loader)
tmp = env.getTemplate()



![[Pasted image 20221201190710.png]]

FileSystemLoader("templates") - устанавливаем локальный путь, я так понял в file_loader будет хранится полный путь до templates

environment () - загрузил загрузил шаблон


![[Pasted image 20221201192111.png]]

