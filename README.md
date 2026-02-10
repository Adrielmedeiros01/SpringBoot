# SpringBoot:
-----------------

- Spring Initializr;
- Maven;
- Criar/Fazer Download do zip(Projeto);
- Pasta Entites;
- Packaging = Jar;
- Configuration = Properties;

- Depedências:
------------------------------------------
      - Lombok;
      - Spring Web;
      - Spring Data JPA;
      - SQL Drive;
------------------------------------------

X
  
  #Criando uma classe(Entidade) dentro da pasta entites:
------------------------------------------
      import lombok.AllArgsConstructor;
      import lombok.Data;
      import lombok.NoArgsConstructor;
      
      //Anotações:
      @Data
      @AllArgsConstructor
      @NoArgsConstructor
      
      public class Categorias {
          private Long id;
          private String descricao;
-----------------------------------------
