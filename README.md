int main() {
    int m[5][5], i, j, op, esc;
    char tipo;
    
    printf("Digite 25 numeros:\n");
    for(i = 0; i < 5; i++)
        for(j = 0; j < 5; j++)
            scanf("%d", &m[i][j]);
            
    printf("\nMatriz:\n");
    for(i = 0; i < 5; i++) {
        for(j = 0; j < 5; j++)
            printf("%2d ", m[i][j]);
        printf("\n");
    }
    printf("\n1-Soma 2-Multiplicacao: ");
    scanf("%d", &op);
    
    printf("\n1-Linhas\n2-Colunas\n3-Diagonal Principal\n4-Diagonal Secundaria\n5-Borda\n6-Internos\n");
    scanf("%d", &esc);

    if(esc == 1) { 
        for(i = 0; i < 5; i++) {
            int res = (op == 1) ? 0 : 1;
            for(j = 0; j < 5; j++)
                op == 1 ? (res += m[i][j]) : (res *= m[i][j]);
            printf("Linha %d: %d\n", i, res);
        }
    }
    else if(esc == 2) { 
        for(j = 0; j < 5; j++) {
            int res = (op == 1) ? 0 : 1;
            for(i = 0; i < 5; i++)
                op == 1 ? (res += m[i][j]) : (res *= m[i][j]);
            printf("Coluna %d: %d\n", j, res);
        }
    }
    else if(esc == 3) { 
        int res = (op == 1) ? 0 : 1;
        for(i = 0; i < 5; i++)
            op == 1 ? (res += m[i][i]) : (res *= m[i][i]);
        printf("Diagonal Principal: %d\n",
        
        int res = (op == 1) ? 0 : 1;
        for(i = 0; i < 5; i++)
            op == 1 ? (res += m[i][4-i]) : (res *= m[i][4-i]);
        printf("Diagonal Secundaria: %d\n", res);
    }
    else if(esc == 5) { 
        int res = (op == 1) ? 0 : 1;
        for(i = 0; i < 5; i++)
            for(j = 0; j < 5; j++)
                if(i == 0 || i == 4 || j == 0 || j == 4)
                    op == 1 ? (res += m[i][j]) : (res *= m[i][j]);
        printf("Borda: %d\n", res);
    }
    else if(esc == 6) { 
        int res = (op == 1) ? 0 : 1;
        for(i = 1; i < 4; i++)
            for(j = 1; j < 4; j++)
                op == 1 ? (res += m[i][j]) : (res *= m[i][j]);
        printf("Internos: %d\n", res);
    }
    else {
        printf("Opcao invalida!");
    }

    return 0;
}
