#SpringBoot:
-----------------

- Spring Initializr: https://start.spring.io/
- Maven;
- Criar/Fazer Download do zip(Projeto);
- Packaging = Jar;
- Configuration = Properties;
- Pasta Entites;
- Pasta Repositories;
- CRUD - CREATE READ UPDATE DELETE;
- Dentro da pasta resources é onde você vai colocar os arquivos HTML,CSS,etc, tamplates,static;
- Criar a classe controller

#Depedências:
------------------------------------------
      - Lombok; -> Ajuda a escrever menos código e gerar algumas coisas automaticamente. (EX: Classes);
      - Spring Web;
      - Spring Data JPA;
      - SQL Drive;
      - Developper tools;
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


#Rodar aplicação:
-----------------------------------------
      
      - Current File;
      - Edit Configuration;

----------------------------------------


#Repositório:
---------------------------------------

      package com.example.demo.repositories;
      
      import com.example.demo.entitees.Categoria;
      import org.springframework.data.repository.CrudRepository;
      import org.springframework.stereotype.Repository;
      
      @Repository
      
      public interface CategoriaRepository extends CrudRepository<Categoria,Long> {
          
      
      }

---------------------------------------

#Aula04/03

---------------------------------------

      package br.edu.ifpe.mecanica.entities;
      
      import jakarta.persistence.Entity;
      import jakarta.persistence.GeneratedValue;
      import jakarta.persistence.GenerationType;
      import jakarta.persistence.Id;
      import lombok.Data;
      
      @Entity
      @Data
      
      public class Cliente {
      
          @Id
          @GeneratedValue(strategy = GenerationType.IDENTITY)
          private Long id;
          private String nome;
          private String celular;
          private String email;
          private String logradouro;
          private String numero;
          private String complemento;
          private String bairro;
          private String cidade;
          private String uf;
          private String cep;
          private String cpfCnpj;  
      
      }


------------------------------------------------------------------------------------------------------------------------------------------------------------

      
      package br.edu.ifpe.mecanica.repositories;
      
      import br.edu.ifpe.mecanica.entities.Cliente;
      import org.springframework.data.repository.CrudRepository;
      import org.springframework.stereotype.Repository;
      
      @Repository
      
      public interface clienteRepository extends CrudRepository<Cliente, Long> {
      
          
      
      }

------------------------------------------------------------------------------------------------------------------------------------------------------------


---------------------------------------

#Aula17/03

---------------------------------------

      * Angular (GOOGLE) - Interessante para coisas mais robustas;
      * Ionic - ;
      * View - ;
      * React (META) - lib - muito utilizado para projetos rapidos;
      * Coreui = Para baixar templates dessas frameWorks;
            - https://coreui.io/
            
      * NO fronte utiliza o VSCode - No back utiliza o InteliJ;

      * npm install -> no terminal - Para fazer algumas instalações;
      * npm start - Para iniciar e vizualiazar o template;
      

------------------------------------------------------------------------------------------------------------------------------------------------------------


