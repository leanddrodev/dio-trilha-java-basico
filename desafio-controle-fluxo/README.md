## Desafio - Controle de Fluxo

O sistema deverá receber dois parâmetros via terminal, que representarão dois números inteiros. A subtração do maior pelo menor determinará a quantidade de interações (for), imprimindo no console os números incrementados a cada laço. Caso o primeiro número seja maior que o primeiro, o sistema lançará uma exceção.

```java
import java.util.Scanner;

public class Contador {

    public static void main(String[] args) {

        Scanner scanner = new Scanner(System.in);

        System.out.println("Digite o primerio parâmetro:");
        int parametroUm = scanner.nextInt();

        System.out.println("Digite o segundo parâmetro:");
        int parametroDois = scanner.nextInt();

        try {
            contar(parametroUm, parametroDois);
        } catch (ParametrosInvalidosException e) {
            System.out.println("O segundo parâmetro deve ser maior que o primeiro");
        }

        scanner.close();

    }

    static void contar(int parametroUm, int parametroDois ) throws ParametrosInvalidosException {
        
        if(parametroUm > parametroDois)
            throw new ParametrosInvalidosException();
        
        int contagem = parametroDois - parametroUm;

        for (int i = 1; i <= contagem; i++)
            System.out.println("Imprimindo o número " + i);

	}

}
```

