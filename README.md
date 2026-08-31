# MVP - Sistema de Suporte à Decisão para Data Centers (SSD)

## 📌 Sobre o Projeto
Este projeto consiste em um Produto Mínimo Viável (MVP) de um Sistema de Suporte à Decisão (SSD). Desenvolvido no contexto prático de Engenharia de Produção da Universidade de Brasília (UnB), o sistema tem como objetivo apoiar a tomada de decisão na viabilidade e implantação de novas unidades de processamento de dados em nuvem (Data Centers).

A ferramenta cruza métricas técnicas de infraestrutura (como uso de CPU, memória, consumo de energia e tráfego de rede) para modelar três dimensões críticas de negócio:
- **Custo**
- **Risco**
- **Tempo**

## 🧠 Lógica e Metodologia
O motor de decisão utiliza uma abordagem multicritério (com conceitos de priorização inspirados no **AHP - Analytic Hierarchy Process**). Diferente de médias simples, os pesos refletem a realidade de engenharia e eficiência energética em data centers:

- **Custo (50%):** Maior peso, dado o alto impacto financeiro do consumo de recursos (CPU e Memória).
- **Risco (30%):** Penaliza configurações com alto tráfego de rede e alto consumo de energia (risco térmico/operacional).
- **Tempo (20%):** Tempo de setup e execução das instâncias.

O sistema compara a entrada do usuário com o histórico da base, calcula a exposição (percentil) de cada variável e emite um veredito final: **FAVORÁVEL, ATENÇÃO ou CRÍTICA**, acompanhado de recomendações estratégicas de planejamento.

## 🗄️ Base de Dados
A base escolhida foi a **Cloud Computing Performance Metrics**, extraída do Kaggle.
A importação é feita dinamicamente via biblioteca `kagglehub`, dispensando o download e upload manual de arquivos CSV.

## 🚀 Como Executar (Google Colab)

1. Faça o upload ou cole o código no **Google Colab**.
2. O sistema exige a instalação da biblioteca do Kaggle. A primeira célula de código fará isso automaticamente:
   ```bash
   !pip install -q "kagglehub[pandas-datasets]"
   ```
3. Execute as células de cima para baixo.
4. Na última célula, teste o SSD informando o Custo (US$), Risco (Score) e Tempo (Dias) estimados para a nova unidade.

## 👨‍💻 Autor
**Pedro Augusto de Menezes Filho**  
*Engenharia de Produção - Universidade de Brasília (UnB)*# SSD_MVP2
