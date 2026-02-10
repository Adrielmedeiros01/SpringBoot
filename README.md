#SpringBoot:
-----------------

- Spring Initializr;
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
      
      @Data
      @AllArgsConstructor
      @NoArgsConstructor
      @Entity //Transforma em uma tabela de banco de dados;
      
      public class Categorias {
      
      //    Sempre fazemos anotações para um atributo, antes dele.

    @Id //Tranforma o primeiro atributo em uma chave primaria;
    @GeneratedValue(strategy = GenerationType.IDENTITY) // Auto Increment - Escolher a estratégia para incrementar;
    private Long id;

    @Column(nullable = false) //Não permtir que a descrição é obrigatória;
    private String descricao;

      }

-----------------------------------------
