# caixa-eletronico
Caixa eletronico

Caixa eletronico com uma login com um CPF(123-456-789-0) e senha(1020304) 
 
import java.util.Scanner;

public class Ac2_Banco_Avila {

    public static void main(String[] args) {

        Scanner ler = new Scanner(System.in);
        int cpfd, menu, s=0;
        int senha = 1020304, cpfc = 1234567890, c, a, b;
        float saldo = 1000, deposito, saque, tra;

        System.out.println("BANCO AVILA\nSeja Bem Vindo!!!");
        System.out.println("123.456.789-0");
        System.out.println("01020304");

        do {
            System.out.print("Digite seu Cpf: ");
            cpfd = ler.nextInt();
            
            if (cpfd != cpfc) {
                System.out.println("CPF INCORRETO");
            }
        } while (cpfd != cpfc);
        {
            for (int i = 1; i <= 3; i++) {
                System.out.print("Digite sua senha: ");
                s = ler.nextInt();
                System.out.println(s);

                if (s == senha) {
                    i = 3;
                    System.out.println("senha correta\n");
                    System.out.println("--------------##--------------\n");
                    System.out.println("             MENU\n");
                    System.out.println("1 - Saldo");
                    System.out.println("2 - Deposito");
                    System.out.println("3 - Saque");
                    System.out.println("4 - Transferencia");
                    System.out.println("0 - Sair\n");
                    do {
                        System.out.print("O que deseja fazer: ");
                        menu = ler.nextInt();

                        switch (menu) {
                            case 1:
                                System.out.println("Saldo Selecionado");
                                System.out.println("Saldo: " + saldo + "R$\n");
                                break;
                            case 2:
                                System.out.println("Deposito Selecionado");
                                System.out.print("Digite o Valor do deposito: ");
                                deposito = ler.nextFloat();
                                saldo = saldo + deposito;
                                System.out.println("Deposito Efetuado\n");
                                System.out.println("Saldo Atual: " + saldo + "R$\n");
                                break;
                            case 3:
                                System.out.println("Saque Selecionado");
                                System.out.print("Digite o Valor do Saque: ");
                                saque = ler.nextFloat();
                                saldo = saldo - saque;
                                System.out.println("Saque Efetuado\n");
                                System.out.println("Saldo Atual: " + saldo + "R$\n");
                                break;
                            case 4:
                                System.out.println("Transferencia Selecionado");
                                System.out.print("Conta:");
                                c = ler.nextInt();
                                System.out.print("Agencia:");
                                a = ler.nextInt();
                                System.out.print("Banco:");
                                b = ler.nextInt();
                                System.out.print("Valor da Transferencia: ");
                                tra = ler.nextFloat();
                                saldo = saldo - tra;
                                System.out.println("\nTransferencia concluida!");
                                System.out.println("Conta: " + c + "\nAgencia: " + a + "\nBanco: " + b + "\nValor: " + tra);
                                System.out.println("\nSaldo Atual: " + saldo + "R$");
                                break;
                            case 0:
                                System.out.println("'Sair'\n");
                                break;
                            default:
                                System.out.println("Digite 1, 2 ou 3!!!");
                                break;
                        }
                    } while (menu != 0);
                    {
                    }
                    System.out.println("O Banco Avila Agradece sua Preferencia");

                } else if (i == 3) {
                    System.out.println("Total tentativas: " + i);
                    System.out.println("SEU CARTAO FOI BLOQUEADO");
                } else if (s != senha) {
                    System.out.println("senha incorreta");
                    System.out.println("Total tentativas: " + i);
                }
            }
        }
    }
}
