## jdbc-java

- Elaborar a estrutura básica de um projeto com JDBC  
- Implementar o padrão DAO manualmente com JDBC  
- Add lib external JAR connector mysql
- API methods para transações:  
setAutoCommit(false)  
commit()  
rollback()  


Script para criação da base inicial de dados:  

CREATE TABLE department (  
  Id int(11) NOT NULL AUTO_INCREMENT,  
  Name varchar(60) DEFAULT NULL,  
  PRIMARY KEY (Id)  
);  

CREATE TABLE seller (  
  Id int(11) NOT NULL AUTO_INCREMENT,  
  Name varchar(60) NOT NULL,  
  Email varchar(100) NOT NULL,  
  BirthDate datetime NOT NULL,  
  BaseSalary double NOT NULL,  
  DepartmentId int(11) NOT NULL,  
  PRIMARY KEY (Id),  
  FOREIGN KEY (DepartmentId) REFERENCES department (id)  
);  

INSERT INTO department (Name) VALUES   
  ('Computers'),  
  ('Electronics'),  
  ('Fashion'),  
  ('Books');  

INSERT INTO seller (Name, Email, BirthDate, BaseSalary, DepartmentId) VALUES   
  ('Bob Brown','bob@gmail.com','1998-04-21 00:00:00',1000,1),  
  ('Maria Green','maria@gmail.com','1979-12-31 00:00:00',3500,2),  
  ('Alex Grey','alex@gmail.com','1988-01-15 00:00:00',2200,1),  
  ('Martha Red','martha@gmail.com','1993-11-30 00:00:00',3000,4),  
  ('Donald Blue','donald@gmail.com','2000-01-09 00:00:00',4000,3),  
  ('Alex Pink','bob@gmail.com','1997-03-04 00:00:00',3000,2); 
  
  API:  
 Statement  
 ResultSet  
o first() [move para posição 1, se houver]  
o beforeFirst() [move para posição 0]  
o next() [move para o próximo, retorna false se já estiver no último]  
o absolute(int) [move para a posição dada, lembrando que dados reais começam em 1]  
