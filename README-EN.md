# HunDunPro

[![](https://img.shields.io/badge/HunDunPro-V2.0.0-gray.svg?longCache=true&colorB=green)](https://pro.hundun.ink/doc) [![](https://img.shields.io/badge/README-ZH-gray.svg?longCache=true&colorB=orange)](./README.md) 

HunDunPro epitomizes a low-code framework forged on Django, empowering the creation of CRUD scripts, interfaces, and frontend vistas by means of database configurations or form-based data inputs.

## Technology Stack
- [x] Python3.12.x
- [x] Django5.x
- [x] Mysql8.x
- [x] Vue2.x
- [ ] Uniapp
- [ ] Flutter

## Project Design
- [x] Backend Interfaces
- [x] Administrative Dashboard
- [x] Frontend Interfaces
- [ ] Mobile Interfaces
- [ ] Mini Programs/H5

## Functional Blueprint
- [x] User Management
- [x] Permission Management
- [x] File Management
- [x] Document Management
- [x] Scheduled Tasks
- [x] Drag-and-Drop Interface Generation
- [x] Code Generation
- [x] Integration of AI Models

## Administrative Dashboard
The administrative dashboard extends the capabilities of Django's built-in Admin dashboard, incorporating enhancements with the aesthetically pleasing `SimpleUI`. It introduces custom actions like exporting and code generation, along with features like rich text editor and JSON editor.
The auto-generated Admin dashboard facilitates a more flexible and efficient management of business operations, significantly reducing the associated development workload.
![admin](https://github.com/user-attachments/assets/61d45d7f-16fc-4d09-90de-18b01f1ae840)

## Code Generation
The code generation functionality is implemented using the `Jinja` templating language, enabling one-click generation of backend interfaces, administrative interfaces, and frontend interfaces. Currently, it supports three modes of code generation: form-editing mode, original code import mode, and database import mode.
![jinja](https://github.com/user-attachments/assets/fcf28f09-758c-4be8-90fb-cc134c3b422c)
### Form Editing Mode
This mode involves designing the data tables and attribute fields of application modules through form editing, with assistance from AI model integration for auxiliary design and related data generation.
![table](https://github.com/user-attachments/assets/37626e85-7844-4f98-99b7-6b11a19d401a)
### Original Code Import Mode
For non-system-generated model code, whether freely written or imported from elsewhere, this mode allows for the selection of module models to import the code segment, generate corresponding data, and then proceed with code generation to complete the generation of interfaces and frontend screens.
![import](https://github.com/user-attachments/assets/89e2c7e0-e029-4d41-b8a9-2c07526e98e6)
### Database Import Mode
Users with a certain level of coding proficiency can freely design SQL databases and then generate corresponding data and code through database import.
![sql](https://github.com/user-attachments/assets/2a9f96bb-39f0-4eaa-8e78-f7d8b1efd5f6)

## Drag-and-Drop Interface Design
We have independently developed a fully open `Drag` directive for implementing drag-and-drop operations and related logic. This enables highly customized low-code drag-and-drop functionality, facilitating efficient frontend interface development.
For non-standard interfaces where the generated form interfaces do not suffice, this tool can be used for interface design and then export the corresponding interface code for utilization.
![web](https://github.com/user-attachments/assets/063b31bf-8608-4c05-a94b-e24d00e01acb)

## Docker Containerized Build and Deployment
The project is containerized with `Docker` for effortless deployment and subsequent regular updates and operations with just a few simple commands.
### Deployment
```
# Docker Deployment and Operations
# Navigate to the project directory
cd /opt/HunDunPro
# Deployment
docker-compose up -d
```
### Updates
```
# Backend Dependency Update (no action required if dependencies remain unchanged)
docker exec hundun pip install --no-cache-dir -r requirements.txt -i https://pypi.doubanio.com/simple
# Backend Data Mapping (no action required if data model remains unchanged)
docker exec hundun python manage.py makemigrations
docker exec hundun python manage.py migrate
# Installation of Frontend Dependencies within the container (no action required if dependencies remain unchanged)
docker exec -it hundun /bin/bash -c "source ~/.nvm/nvm.sh && cd /pro/HunDunPro/hundun-web && npm install --registry=https://registry.npmmirror.com"
# Frontend Packaging
docker exec -it hundun /bin/bash -c "source ~/.nvm/nvm.sh && cd /pro/HunDunPro/hundun && python manage.py build"
# Update
git pull
docker-compose restart
```

## Cross-Platform Design
This project is under continuous development and enhancement for mobile platforms and beyond...
![hundun](https://github.com/user-attachments/assets/2971eb86-e33e-4d4a-94ae-3dc7bc73a55a)

