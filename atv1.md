```pseudo
INICIAR programa_lavar_roupas

    // Definição de Variáveis
    VAR roupas, detergente, amaciante, agua, temperatura, tempo_lavagem, modo_lavagem, centrifugacao, energia_eletrica
    
    // Preparação
    SEPARAR roupas por cor e tipo de tecido
    
    // Carregar a máquina
    COLOCAR roupas na máquina
    ADICIONAR detergente no compartimento
    SE amaciante desejado ENTÃO adicionar amaciante
    
    // Seleção do Programa
    SELECIONAR modo_lavagem
        SE roupas forem delicadas ENTÃO modo_lavagem = delicado
        SENÃO SE roupas forem pesadas ENTÃO modo_lavagem = pesado
        SENÃO modo_lavagem = normal
        
    SELECIONAR temperatura
        SE roupas forem coloridas ENTÃO temperatura = fria
        SENÃO SE roupas brancas ENTÃO temperatura = morna
        SENÃO temperatura = quente
        
    DEFINIR tempo_lavagem
        SE modo_lavagem = delicado ENTÃO tempo_lavagem = 30 minutos
        SENÃO SE modo_lavagem = pesado ENTÃO tempo_lavagem = 60 minutos
        SENÃO tempo_lavagem = 45 minutos

    // Iniciar Ciclo de Lavagem
    SE energia_eletrica disponível ENTÃO
        LIGAR máquina
        ADICIONAR agua automaticamente com base na quantidade de roupas
        
        // Ciclo de Lavagem
        ENQUANTO tempo_lavagem > 0 FAZER
            LAVAR roupas
            DIMINUIR tempo_lavagem
        FIM ENQUANTO

        // Centrifugação
        INICIAR centrifugacao
        AGUARDAR fim da centrifugacao
    SENÃO
        EXIBIR "Erro: sem energia elétrica"
    
    // Finalização
    EMITIR sinal de término
    DESLIGAR máquina
    ABRIR tambor e RETIRAR roupas
    
    // Secagem (Opcional)
    SE secagem_manual ENTÃO
        PENDURAR roupas no varal
    SENÃO SE usar_secadora ENTÃO
        COLOCAR roupas na secadora

FIM programa_lavar_roupas
