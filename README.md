# Parcial

> Script de la base de datos
```sql

    DROP DATABASE IF EXISTS SistemaDeRecordatorioPersonalizado;

    CREATE DATABASE SistemaDeRecordatorioPersonalizado;

    USE SistemaDeRecordatorioPersonalizado;

    CREATE table User(
        Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        País VARCHAR(50) NOT NULL,
        Primer nombre VARCHAR(50) NOT NULL,
        Segundo nombre VARCHAR(50) NOT NULL,
        Contraseña VARCHAR(50) NOT NULL,
        Rol VARCHAR(50) NOT NULL,
        Username VARCHAR(50) NOT NULL,
        
    ); 

    CREATE table Categoria(
        Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        Descripcion VARCHAR(50) NOT NULL,
        User_Id INT NOT NULL,
        FOREIGN KEY (User_Id) REFERENCES User(Id)
    ); 

    CREATE table Recordatorio(
        Id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
        Archivo VARCHAR(50) NOT NULL,
        Descripcion VARCHAR(50) NOT NULL ,
        Fecha DATE NOT NULL,
        Hora DATETIME,
        Titulo VARCHAR(50) NOT NULL ,
        Categoria_Id INT NOT NULL,
        FOREIGN KEY (Categoria_Id) REFERENCES Categoria(Id)
        
    );