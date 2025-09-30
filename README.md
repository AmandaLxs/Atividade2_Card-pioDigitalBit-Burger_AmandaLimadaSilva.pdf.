#include <stdio.h>

int main() {
    // -----------------------------
    // Declaração das variáveis
    // -----------------------------
    int categoria;     // Categoria escolhida: 1-Pratos, 2-Bebidas, 3-Sobremesas, 4-Finalizar
    int item;          // Item escolhido dentro da categoria
    int quantidade;    // Quantidade do item escolhido
    float total = 0.0; // Total acumulado do pedido
    char continuar = 's'; // Controle do loop principal (s = continuar, n = finalizar)

    // -----------------------------
    // Boas-vindas
    // -----------------------------
    printf("============================================\n");
    printf("      Bem-vindo ao Bit & Burger!            \n");
    printf("  Escolha seus pratos, bebidas e sobremesas.\n");
    printf("============================================\n\n");

    // -----------------------------
    // Loop principal do menu
    // -----------------------------
    while (continuar == 's' || continuar == 'S') {

        // Exibe as categorias
        printf("\nEscolha a categoria:\n");
        printf("1. Pratos\n");
        printf("2. Bebidas\n");
        printf("3. Sobremesas\n");
        printf("4. Finalizar Pedido\n");
        printf("Opção: ");
        scanf("%d", &categoria);

        // -----------------------------
        // Estrutura de decisão para cada categoria
        // -----------------------------
        switch(categoria) {

            // ---------- Pratos ----------
            case 1:
                printf("\nPratos:\n");
                printf("0. Não quero nenhum prato\n");
                printf("1. Burger da Casa - R$ 32.90\n");
                printf("2. Frango Dourado - R$ 28.50\n");
                printf("3. Massa Cremosa - R$ 34.00\n");
                printf("Escolha o prato (0-3): ");
                scanf("%d", &item);

                // Se o usuário não quer nenhum prato
                if(item == 0) { 
                    printf("Ok, você não escolheu nenhum prato.\n"); 
                    break; 
                }

                // Solicita quantidade
                printf("Quantidade: ");
                scanf("%d", &quantidade);

                // Calcula subtotal e adiciona ao total
                if(item == 1) total += 32.90 * quantidade;
                else if(item == 2) total += 28.50 * quantidade;
                else if(item == 3) total += 34.00 * quantidade;
                else printf("Opção inválida!\n");
                break;

            // ---------- Bebidas ----------
            case 2:
                printf("\nBebidas:\n");
                printf("0. Não quero nenhuma bebida\n");
                printf("1. Suco Natural - R$ 8.00\n");
                printf("2. Refrigerante Lata - R$ 6.50\n");
                printf("3. Água com/sem gás - R$ 4.00\n");
                printf("Escolha a bebida (0-3): ");
                scanf("%d", &item);

                if(item == 0) { 
                    printf("Ok, você não escolheu nenhuma bebida.\n"); 
                    break; 
                }

                printf("Quantidade: ");
                scanf("%d", &quantidade);

                if(item == 1) total += 8.00 * quantidade;
                else if(item == 2) total += 6.50 * quantidade;
                else if(item == 3) total += 4.00 * quantidade;
                else printf("Opção inválida!\n");
                break;

            // ---------- Sobremesas ----------
            case 3:
                printf("\nSobremesas:\n");
                printf("0. Não quero nenhuma sobremesa\n");
                printf("1. Brownie da Casa - R$ 18.00\n");
                printf("2. Cheesecake - R$ 19.50\n");
                printf("3. Mousse de Maracujá - R$ 15.00\n");
                printf("Escolha a sobremesa (0-3): ");
                scanf("%d", &item);

                if(item == 0) { 
                    printf("Ok, você não escolheu nenhuma sobremesa.\n"); 
                    break; 
                }

                printf("Quantidade: ");
                scanf("%d", &quantidade);

                if(item == 1) total += 18.00 * quantidade;
                else if(item == 2) total += 19.50 * quantidade;
                else if(item == 3) total += 15.00 * quantidade;
                else printf("Opção inválida!\n");
                break;

            // ---------- Finalizar Pedido ----------
            case 4:
                printf("\n======= RESUMO DO PEDIDO =======\n");
                printf("Total do pedido: R$ %.2f\n", total);

                // Desconto simples se total > 80
                if(total > 80.0){
                    printf("Desconto de 10%% aplicado!\n");
                    total *= 0.9;
                }

                // Frete grátis se total > 100
                if(total > 100.0) printf("Parabéns! Frete grátis!\n");

                printf("\nTotal final: R$ %.2f\n", total);
                printf("Obrigado por pedir no Bit & Burger! Volte sempre!\n");
                return 0;

            // Opção inválida
            default:
                printf("Opção inválida! Tente novamente.\n");
        }

        // -----------------------------
        // Pergunta se deseja continuar no menu
        // -----------------------------
        printf("\nDeseja adicionar mais itens? (s/n): ");
        scanf(" %c", &continuar);
    }

    return 0;
}
