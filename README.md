# 📊 Pesquisa de Satisfação de Atendimento — TudoWeb

Projeto desenvolvido como parte do módulo de Algoritmos e Estruturas de Repetição. O objetivo é coletar a opinião dos clientes da empresa de marketing **TudoWeb** sobre o atendimento recebido e gerar um resumo estatístico das respostas.

---

## 🛠️ Funcionalidades

- Coleta de dados individuais (nome e idade).
- Registro da opinião sobre o atendimento:
  - `1` - EXCELENTE
  - `2` - BOM
  - `3` - RUIM
- Contabilização automatizada de métricas principais (Total de avaliações "EXCELENTE" "BOM" e "RUIM").
- Validação de dados de entrada via estruturas condicionais.

---

## 💻 Tecnologias Utilizadas

- **Linguagem:** Python 3
- **Conceitos Aplicados:**
  - Estruturas de Repetição Dinâmicas (`while True`, `break`)
  - Estruturas de Decisão (`if`, `elif`, `else`)
  - Manipulação de Strings (`.strip()`, `.upper()`)
  - Entradas e Saídas via Console (`input`, `print`)
  - Manipulação e conversão de tipos de dados (`int`)

---

## 🌟 Diferenciais do Projeto

- **Coleta Sem Limite Fixo:** Uso de laço `while` interativo para permitir o cadastro de qualquer quantidade de entrevistados.
- **Relatório Completo (100% dos Dados):** Além das métricas solicitadas (`EXCELENTE` e `RUIM`), o programa contabiliza as respostas `BOM`, garantindo total precisão nos resultados em relação ao número de entrevistados.

---

## 🚀 Como Executar o Projeto

1. Certifique-se de ter o [Python](https://www.python.org/) instalado.
2. Cole este repositório:
```python
# =========================================
# EMPRESA DE MARKETING: TUDOWEB
# Projeto: Pesquisa de Satisfação no Atendimento (Com contagem da opção BOM)
# =========================================

# Inicializamos os três contadores
qtd_excelente = 0
qtd_bom = 0       # Adicionado contador para a opção BOM
qtd_ruim = 0
total_entrevistados = 0

print("=" * 50)
print("       PESQUISA DE SATISFAÇÃO - TUDOWEB")
print("=" * 50)

# ESTRUTURA DE REPETIÇÃO
while True:
    total_entrevistados += 1
    print(f"\n--- Entrevistado {total_entrevistados} ---")
    
    nome = input("Digite o nome: ")
    idade = int(input("Digite a idade: "))

    print("\nQual a sua opinião sobre o atendimento?")
    print("  [1] EXCELENTE")
    print("  [2] BOM")
    print("  [3] RUIM")
    
    opiniao = int(input("Digite sua opção (1, 2 ou 3): "))

    # ESTRUTURA CONDICIONAL
    if opiniao == 1:
        qtd_excelente += 1
    elif opiniao == 2:
        qtd_bom += 1       # Agora soma +1 quando a opção for 2 (BOM)
    elif opiniao == 3:
        qtd_ruim += 1
    else:
        print(">> Opção inválida! Esta resposta não será contabilizada.")

    # PERGUNTA DE PARADA
    continuar = input("\nDeseja cadastrar outro entrevistado? (S/N): ").strip().upper()
    
    if continuar == 'N':
        print("\nEncerrando a coleta de dados...")
        break

# EXIBIÇÃO DOS RESULTADOS FINAIS
print("\n" + "=" * 50)
print("             RESULTADO DA PESQUISA")
print("=" * 50)
print(f"Total de entrevistados: {total_entrevistados}")
print(f"a) Respostas 'EXCELENTE': {qtd_excelente}")
print(f"b) Respostas 'BOM':       {qtd_bom}")        # Linha exibindo a contagem de BOM
print(f"c) Respostas 'RUIM':      {qtd_ruim}")
print("=" * 50)
