#SpringBoot:
-----------------

- Spring Initializr: https://start.spring.io/
- Maven;
- Criar/Fazer Download do zip(Projeto);
- Packaging = Jar;
- Configuration = Properties;
- Pasta Entites;

#Depedências:
------------------------------------------
      - Lombok;
      - Spring Web;
      - Spring Data JPA;
      - SQL Drive;
------------------------------------------
  
#Criando uma classe(Entidade) dentro da pasta entites:
------------------------------------------
     package com.example.demo.entitees;

      import jakarta.persistence.*;
      import lombok.AllArgsConstructor;
      import lombok.Data;
      import lombok.NoArgsConstructor;
      
      //Anotações (Sempre começam com '@'):
      
      @Data // Get e Set - automaticas;
      @AllArgsConstructor // Cria todos os argumentos do Cosntrutor;
      @NoArgsConstructor
      @Entity //Transforma em uma tabela de banco de dados;
      
      public class Categorias {
      
      //    Sempre fazemos anotações para um atributo, antes dele.
      
          @Id //Tranforma o próximo atributo em uma chave primaria;
          @GeneratedValue(strategy = GenerationType.IDENTITY) // Auto Increment - Escolher a estratégia para incrementar;
          private Long id;
      
          @Column(nullable = false) //Define a descrição como obrigatória;
          private String descricao;
      
      }


      ------------------------------------------------------------------------------------------------


      package com.example.demo.entitees;
      
      
      import jakarta.persistence.*;
      import lombok.Data;
      
      @Data //Get e Set;
      @Entity //Vira uma entidade;
      
      public class Produto {
      
          @Id
          @GeneratedValue(strategy = GenerationType.IDENTITY)
          private Long id;
          @Column(nullable = false)
          private String descricao;
          private double preco;
          private Long codBar;
          @ManyToOne // Tipo de chave estrangeira (Mapeamento)
          private Categoria categoria;
      
      }


-----------------------------------------


#Sobre Banco de Dados e a Comunicação:


-----------------------------------------

      spring.application.name=demo
      
      # Altera a estrutura da tabela caso a entidade tenha mudanças. Lembra doHibernate?
      spring.jpa.hibernate.ddl-auto=update
      
      # Acesso ao banco de dados defindo o SGBD e a Base de dados. Mude o nome da sua base
      spring.datasource.url=jdbc:mysql://${MYSQL_HOST:localhost}:3306/biblioteca
      
      # Usuário do banco de dados
      spring.datasource.username=usuarioBiblioteca
      
      # Senha do banco de dados
      spring.datasource.password=123


      
-----------------------------------------



