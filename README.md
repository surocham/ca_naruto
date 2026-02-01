# 🥷 Análise de Correspondência Simples — Mundo Naruto

Um projeto completo de Análise de Correspondência Simples (CA) usando Python, onde exploramos as relações entre as aldeias do mundo Naruto e os estilos de luta dos shinobis.

---

## 📁 Estrutura do Projeto

```
projeto/
├── tabela_contingencia_naruto.csv          # Dados brutos
├── analise_correspondencia_naruto.ipynb    # Notebook com a análise passo a passo
├── biplot_cores_associadas.py              # Script do biplot com cores associadas
└── README.md                               # Este arquivo
```

---

## 📦 Dependências

```bash
pip install pandas numpy matplotlib seaborn scipy
```

Para o bônus com Prince:

```bash
pip install prince
```

---

## 🚀 Como Rodar

1. Clone ou baixe todos os arquivos na mesma pasta
2. Abra o notebook `analise_correspondencia_naruto.ipynb` no Jupyter ou Google Colab
3. Execute as células na ordem — cada uma representa um passo da análise


---

## 📊 O que é feito na análise

A análise segue 9 passos dentro do notebook:

| Passo | O que acontece | Analogia Naruto |
|-------|----------------|-----------------|
| 1 | Importação de bibliotecas | Reunir o squad |
| 2 | Carregamento dos dados | Ler o relatório da missão |
| 3 | Tabela de contingência | Ver quantos shinobis de cada aldeia preferem cada estilo |
| 4 | Perfis de linha e coluna | Montar o "perfil de combate" de cada aldeia |
| 5 | Teste Qui-Quadrado | Confirmar que a associação não é coincidência |
| 6 | Resíduos padronizados | Encontrar os "Rock Lees" dos dados |
| 7 | Decomposição SVD | Usar o Sharingan — focar no que importa |
| 8 | Mapa de Correspondência | Desenhar o mapa final do mundo dos shinobis |
| 9 | Interpretação | Entender quem se pareça com quem |

---

## 🗺️ Como interpretar o Biplot

- **Círculos** = aldeias
- **Quadrados** = estilos de luta
- **Cores iguais** = aldeia e estilo mais associados entre si (calculado automaticamente pelos resíduos)
- **Pontos próximos** = relação forte
- **Pontos longe** = relação fraca
- **Centro (origem)** = ponto neutro, sem associação forte

As associações encontradas nos dados:

| Aldeia | Estilo mais associado | Por quê faz sentido |
|--------|-----------------------|---------------------|
| Konoha | Taijutsu | Rock Lee, Guy-Sensei |
| Kiri | Senjutsu | Técnicas avançadas dos shinobis de Kiri |
| Ame | Ninjutsu | Aldeia da chuva, manipulação de natureza |
| Suna | Genjutsu | Perfil mais equilibrado, mas destaca aqui |

---

## 🎌 Bônus: Biblioteca Prince

O Prince simplifica toda a parte matemática em poucas linhas. Em vez de calcular a SVD manualmente, você faz apenas:

```python
import prince

ca = prince.CA(n_components=2)
ca = ca.fit(data)

# Coordenadas já prontas
print(ca.row_coordinates(data))
print(ca.column_coordinates(data))

# Inércia explicada
print(ca.percentage_of_variance_)
```

É como a diferença entre um genin aprendendo Taijutsu passo a passo e um jounin executando a técnica em um segundo. Mas entender a implementação manual primeiro é fundamental antes de partir para o Prince.

---

## 📚 Referências

- Greenacre, M. (2017). *Correspondence Analysis in Practice*. Chapman and Hall/CRC.
- [Prince — GitHub](https://github.com/MaxHalford/prince)
- [Pandas Documentation](https://pandas.pydata.org)
- [Seaborn Documentation](https://seaborn.pydata.org)
