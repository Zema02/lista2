7
```pseudocode
Início
    Ler valorTotalCompra
    Se (valorTotalCompra < 50) então
        Escrever "Frete não disponível!"
    Senão se (valorTotalCompra >= 50 e valorTotalCompra <= 199.99) então
        Escrever "Frete com custo adicional!"
    Senão
        Escrever "Frete grátis!"
    FimSe
Fim



8

// Classe Base
Classe Veiculo:
    Atributos:
        modelo, ano
    Método Construtor(modelo, ano):
        this.modelo ← modelo
        this.ano ← ano
    Método CalcularConsumo():
        Retornar "Consumo não especificado"

// Classe Carro
Classe Carro herda de Veiculo:
    Atributos:
        quilometragem, eficienciaCarro
    Método Construtor(modelo, ano, quilometragem, eficienciaCarro):
        Chamar construtor de Veiculo(modelo, ano)
        this.quilometragem ← quilometragem
        this.eficienciaCarro ← eficienciaCarro
    Método CalcularConsumo():
        Retornar quilometragem / eficienciaCarro

// Classe Moto
Classe Moto herda de Veiculo:
    Atributos:
        quilometragem, eficienciaMoto
    Método Construtor(modelo, ano, quilometragem, eficienciaMoto):
        Chamar construtor de Veiculo(modelo, ano)
        this.quilometragem ← quilometragem
        this.eficienciaMoto ← eficienciaMoto
    Método CalcularConsumo():
        Retornar quilometragem / eficienciaMoto

        9
        Início
    Ler velocidadeInicial, velocidadeSegura, desaceleracao, tempoMaximo
    tempo ← 0
    velocidade ← velocidadeInicial
    Enquanto (velocidade > velocidadeSegura e tempo < tempoMaximo) faça:
        tempo ← tempo + intervaloDeTempo
        velocidade ← velocidadeInicial - desaceleracao * tempo
        Se (velocidade < velocidadeSegura) então:
            velocidade ← velocidadeSegura
        FimSe
    FimEnquanto
    Se (tempo >= tempoMaximo) então:
        Escrever "Tempo máximo de descida atingido sem atingir velocidade segura."
    Senão:
        Escrever "Tempo necessário para pouso seguro: ", tempo, " segundos."
Fim


10

Função MultiplicarMatrizesInvestimento(matrizA, matrizB):
    Se (colunas(matrizA) ≠ linhas(matrizB)) então:
        Retornar "Dimensões incompatíveis."
    linhasResultado ← linhas(matrizA)
    colunasResultado ← colunas(matrizB)
    matrizResultado ← novaMatriz(linhasResultado, colunasResultado)
    Para i de 0 até linhasResultado - 1 faça:
        Para j de 0 até colunasResultado - 1 faça:
            matrizResultado[i][j] ← 0
            Para k de 0 até colunas(matrizA) - 1 faça:
                matrizResultado[i][j] ← matrizResultado[i][j] + (matrizA[i][k] * matrizB[k][j])
            FimPara
        FimPara
    Retornar matrizResultado
