Exercício 1: Impressão de Números de 1 a 50

public class Ex1_While {
    public static void main(String[] args) {
        int i = 1;
        while (i <= 50) {
            System.out.println(i);
            i++;
        }
    }
}

Exercício 2: Soma de Números Positivos

import java.util.Scanner;

public class Ex2_While {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int numero;
        int soma = 0;

        System.out.println("Digite números positivos (negativo para parar):");

        while ((numero = sc.nextInt()) >= 0) {
            soma += numero;
        }

        System.out.println("Soma dos números positivos: " + soma);
        sc.close();
    }
}

Exercício 3: Validação de Senha

import java.util.Scanner;

public class Ex3_While {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        final String senhaCorreta = "1234";
        String senha;

        do {
            System.out.print("Digite a senha: ");
            senha = sc.nextLine();
            if (!senha.equals(senhaCorreta)) {
                System.out.println("Senha incorreta, tente novamente.");
            }
        } while (!senha.equals(senhaCorreta));

        System.out.println("Acesso concedido");
        sc.close();
    }
}

Exercício 4: Sequência de Fibonacci (10 primeiros números)

public class Ex4_While {
    public static void main(String[] args) {
        int a = 0, b = 1, count = 0;
        while (count < 10) {
            System.out.println(a);
            int temp = a + b;
            a = b;
            b = temp;
            count++;
        }
    }
}

Exercícios simulando do..while
Exercício 1: Validação de Entrada de Dados

import java.util.Scanner;

public class DoWhile1 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int numero;

        do {
            System.out.print("Digite um número entre 1 e 100: ");
            numero = sc.nextInt();
        } while (numero < 1 || numero > 100);

        System.out.println("Número válido: " + numero);
        sc.close();
    }
}

Exercício 2: Menu Interativo

import java.util.Scanner;

public class DoWhile2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int opcao;

        do {
            System.out.println("\n1 - Adicionar\n2 - Remover\n3 - Sair");
            System.out.print("Escolha uma opção: ");
            opcao = sc.nextInt();

            switch (opcao) {
                case 1 -> System.out.println("Item adicionado!");
                case 2 -> System.out.println("Item removido!");
                case 3 -> System.out.println("Saindo...");
                default -> System.out.println("Opção inválida!");
            }
        } while (opcao != 3);

        sc.close();
    }
}

Exercício 3: Jogo de Adivinhação

import java.util.Scanner;
import java.util.Random;

public class DoWhile3 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Random rand = new Random();
        int numeroSecreto = rand.nextInt(20) + 1;
        int tentativa, tentativas = 0;

        do {
            System.out.print("Adivinhe o número (1 a 20): ");
            tentativa = sc.nextInt();
            tentativas++;

            if (tentativa < numeroSecreto) {
                System.out.println("Muito baixo!");
            } else if (tentativa > numeroSecreto) {
                System.out.println("Muito alto!");
            }

        } while (tentativa != numeroSecreto);

        System.out.println("Parabéns! Você acertou em " + tentativas + " tentativa(s).");
        sc.close();
    }
}

Exercício 4: Cálculo de Média de Notas

import java.util.Scanner;

public class DoWhile4 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String continuar;
        double nota, soma = 0;
        int contador = 0;

        do {
            System.out.print("Digite uma nota (0 a 10): ");
            nota = sc.nextDouble();

            if (nota >= 0 && nota <= 10) {
                soma += nota;
                contador++;
            } else {
                System.out.println("Nota inválida.");
            }

            System.out.print("Deseja inserir outra nota? (s/n): ");
            continuar = sc.next();

        } while (continuar.equalsIgnoreCase("s"));

        if (contador > 0) {
            System.out.printf("Média das notas: %.2f\n", soma / contador);
        } else {
            System.out.println("Nenhuma nota válida foi inserida.");
        }

        sc.close();
    }

    
exercícios com for

Exercício 1: Tabela de Multiplicação do 5

public class For1 {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            System.out.println("5 x " + i + " = " + (5 * i));
        }
    }
}

Exercício 2: Cálculo de Fatorial

import java.util.Scanner;

public class For2 {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Digite um número inteiro positivo: ");
        int num = sc.nextInt();
        long fatorial = 1;

        for (int i = 1; i <= num; i++) {
            fatorial *= i;
        }

        System.out.println("Fatorial de " + num + " = " + fatorial);
        sc.close();
    }
}

Exercício 3: Soma de Elementos em um Vetor

public class For3 {
    public static void main(String[] args) {
        int[] vetor = {5, 10, 15, 2, 3, 8, 7, 1, 12, 9};
        int soma = 0;

        for (int num : vetor) {
            soma += num;
        }

        System.out.println("Soma dos elementos: " + soma);
    }
}
Exercício 4: Impressão de Números Ímpares
java
Copiar
Editar
public class For4 {
    public static void main(String[] args) {
        for (int i = 1; i <= 100; i++) {
            if (i % 2 != 0) {
                System.out.println(i);
            }
        }
    }
}

 Desafio: Calculadora de Rendimento

import java.util.Scanner;

public class CalculadoraRendimento {

    public static double calcularSimples(double P, double r, int t) {
        return P * (1 + (r / 100) * t);
    }

    public static double calcularComposto(double P, double r, int t) {
        return P * Math.pow(1 + (r / 100), t);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        String continuar;

        do {
            System.out.print("Valor do investimento inicial (P): ");
            double P = sc.nextDouble();

            System.out.print("Taxa de juros anual (%) (r): ");
            double r = sc.nextDouble();

            System.out.print("Período em anos (t): ");
            int t = sc.nextInt();

            System.out.print("Tipo de capitalização (simples ou composta): ");
            String tipo = sc.next();

            double montante = 0;
            if (tipo.equalsIgnoreCase("simples")) {
                montante = calcularSimples(P, r, t);
            } else if (tipo.equalsIgnoreCase("composta")) {
                montante = calcularComposto(P, r, t);
            } else {
                System.out.println("Tipo inválido.");
                continue;
            }

            System.out.printf("Montante final: R$ %.2f\n", montante);

            System.out.print("Deseja realizar outro cálculo? (s/n): ");
            continuar = sc.next();
        } while (continuar.equalsIgnoreCase("s"));

        sc.close();
    }
}
