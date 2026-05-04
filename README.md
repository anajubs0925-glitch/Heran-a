public class Main {
    public static void main(String[] args) {

        // Criando objetos para testar
        Aluno aluno = new Aluno("Ana", "9999-9999", "123456789", 101);
        Professor prof = new Professor("Carlos", "8888-8888", "987654321", "Mestre");
        Funcionario func = new Funcionario("João", "7777-7777", "111222333", 1, "Secretário");

        Responsavel resp = new Responsavel(aluno);

        // Testando métodos
        aluno.aprender();
        prof.ensinar();
        func.desempenharFuncao();

        aluno.documento();
    }
}

// Classe base
class Pessoa {
    String nome;
    String fone;
    String cpf;

    Pessoa(String nome, String fone, String cpf) {
        this.nome = nome;
        this.fone = fone;
        this.cpf = cpf;
    }

    void documento() {
        System.out.println("Documento: " + cpf);
    }
}

// Herança
class Funcionario extends Pessoa {
    int cod;
    String funcao;

    Funcionario(String nome, String fone, String cpf, int cod, String funcao) {
        super(nome, fone, cpf);
        this.cod = cod;
        this.funcao = funcao;
    }

    void desempenharFuncao() {
        System.out.println("Função: " + funcao);
    }
}

class Aluno extends Pessoa {
    int matricula;

    Aluno(String nome, String fone, String cpf, int matricula) {
        super(nome, fone, cpf);
        this.matricula = matricula;
    }

    void aprender() {
        System.out.println(nome + " está aprendendo...");
    }
}

class Professor extends Pessoa {
    String titulo;

    Professor(String nome, String fone, String cpf, String titulo) {
        super(nome, fone, cpf);
        this.titulo = titulo;
    }

    void ensinar() {
        System.out.println(nome + " está ensinando...");
    }
}

// Associação
class Responsavel {
    Aluno aluno;

    Responsavel(Aluno aluno) {
        this.aluno = aluno;
    }
}
