# SpringBoot:
-----------------

- Spring Initializr;
- Maven;
- Criar/Fazer Download do zip(Projeto);
- Pasta Entites;

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
