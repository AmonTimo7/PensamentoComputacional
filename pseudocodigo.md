Pseudocódigos - Nível 3 (Abstração Computacional)

INICIO Algoritmo CriarContrato

dados_cliente <- ler_formulario_contrato()

SE (dados_cliente.nome != "" E dados_cliente.cpf != "" E dados_cliente.valor_total > 0) ENTAO
 
    estado_salvamento <- enviar_para_banco_de_dados_api(dados_cliente)
    
    SE (estado_salvamento == FALHA_CONEXAO) ENTAO
        salvar_armazenamento_local(dados_cliente)
    FIM SE
    
    limpar_campos_formulario()
    fechar_modal_interface()
    atualizar_lista_contratos()

SENAO
    exibir_alerta("Preencha todos os campos obrigatórios")
FIM SE

FIM Algoritmo

