# Marvel DB: Banco de Dados de Produções da Marvel

Bem-vindo ao **Marvel DB**!  
Este repositório oferece um script SQL completo, projetado para criar e popular um banco de dados com uma vasta coleção de produções do universo Marvel.  
A lista abrange desde o Universo Cinematográfico Marvel (MCU) até produções de outros estúdios como Sony Pictures, 20th Century Fox e New Line Cinema, incluindo filmes, séries e animações.

---

## 📜 Sobre o Projeto

O objetivo deste projeto é centralizar informações essenciais sobre as produções da Marvel em um único banco de dados relacional.  
Ele foi criado para ser uma ferramenta útil para:

- Desenvolvedores  
- Analistas de dados  
- Fãs que desejam consultar, analisar ou criar aplicações baseadas no rico universo da Marvel

---

## 📊 Estrutura da Tabela

O script opera sobre uma única tabela chamada `Producoes_Marvel`, com a seguinte estrutura:

| Coluna              | Tipo               | Descrição                                                       |
|---------------------|--------------------|------------------------------------------------------------------|
| `ID`                | INT, PRIMARY KEY   | Identificador único para cada produção (auto-incremento)         |
| `Titulo`            | VARCHAR(255)       | O título oficial da produção                                     |
| `Tipo`              | VARCHAR(20)        | O formato da produção (`Filme`, `Série` ou `Animação`)           |
| `Ano`               | INT                | O ano de lançamento original                                     |
| `Estudio`           | VARCHAR(100)       | O principal estúdio responsável pela produção                    |
| `Diretor_Criador`   | VARCHAR(255)       | O(s) diretor(es) ou criador(es) da produção                      |
| `Duracao_Episodios` | VARCHAR(20)        | A duração total (filmes) ou número de episódios (séries)         |
| `Classificacao`     | VARCHAR(10)        | A classificação indicativa (varia por região)                   |
| `Conexao_MCU`       | BOOLEAN            | Indica se faz parte do canon principal do MCU                   |
| `Sinopse`           | TEXT               | Um breve resumo do enredo                                        |

---

## 🎬 Conteúdo do Banco de Dados

A base de dados inclui títulos organizados da seguinte forma:

### Universo Cinematográfico Marvel (MCU)

#### 🧪 A Saga do Infinito:

- Homem de Ferro (2008)  
- O Incrível Hulk (2008)  
- Homem de Ferro 2 (2010)  
- Thor (2011)  
- Capitão América: O Primeiro Vingador (2011)  
- Os Vingadores (2012)  
- Homem de Ferro 3 (2013)  
- Thor: O Mundo Sombrio (2013)  
- Capitão América: O Soldado Invernal (2014)  
- Guardiões da Galáxia (2014)  
- Vingadores: Era de Ultron (2015)  
- Homem-Formiga (2015)  
- Capitão América: Guerra Civil (2016)  
- Doutor Estranho (2016)  
- Guardiões da Galáxia Vol. 2 (2017)  
- Homem-Aranha: De Volta ao Lar (2017)  
- Thor: Ragnarok (2017)  
- Pantera Negra (2018)  
- Vingadores: Guerra Infinita (2018)  
- Homem-Formiga e a Vespa (2018)  
- Capitã Marvel (2019)  
- Vingadores: Ultimato (2019)  
- Homem-Aranha: Longe de Casa (2019)  

#### 🌌 A Saga do Multiverso:

- Viúva Negra (2021)  
- Shang-Chi e a Lenda dos Dez Anéis (2021)  
- Eternos (2021)  
- Homem-Aranha: Sem Volta Para Casa (2021)  
- Doutor Estranho no Multiverso da Loucura (2022)  
- Thor: Amor e Trovão (2022)  
- Pantera Negra: Wakanda Para Sempre (2022)  
- Homem-Formiga e a Vespa: Quantumania (2023)  
- Guardiões da Galáxia Vol. 3 (2023)  
- As Marvels (2023)  

#### 📺 Séries Disney+:

- WandaVision (2021)  
- Falcão e o Soldado Invernal (2021)  
- Loki (2021)  
- Gavião Arqueiro (2021)  
- Cavaleiro da Lua (2022)  
- Ms. Marvel (2022)  
- Mulher-Hulk: Defensora de Heróis (2022)  
- Invasão Secreta (2023)  
- Echo (2024)  

#### 🎨 Animações do MCU:

- What If...? (2021)  
- Eu Sou Groot (2022)  
- X-Men '97 (2024)  

---

### Outras Produções Marvel (Não-MCU)

#### 🎥 Filmes (Sony, 20th Century Fox, etc.):

- Blade: O Caçador de Vampiros (1998)  
- X-Men: O Filme (2000)  
- Homem-Aranha (2002)  
- Demolidor - O Homem Sem Medo (2003)  
- X-Men 2 (2003)  
- Hulk (2003)  
- Homem-Aranha 2 (2004)  
- O Justiceiro (2004)  
- X-Men: O Confronto Final (2006)  
- Motoqueiro Fantasma (2007)  
- Homem-Aranha 3 (2007)  
- Quarteto Fantástico e o Surfista Prateado (2007)  
- X-Men Origens: Wolverine (2009)  
- X-Men: Primeira Classe (2011)  
- O Espetacular Homem-Aranha (2012)  
- Wolverine: Imortal (2013)  
- X-Men: Dias de um Futuro Esquecido (2014)  
- Deadpool (2016)  
- X-Men: Apocalipse (2016)  
- Logan (2017)  
- Venom (2018)  
- Deadpool 2 (2018)  
- X-Men: Fênix Negra (2019)  
- Os Novos Mutantes (2020)  

#### 🕸️ Animações:

- Homem-Aranha no Aranhaverso (2018)  

---

## ⚙️ Como Usar

### 1. Crie a Tabela

Execute o seguinte comando no seu banco de dados (MySQL, PostgreSQL, SQL Server, etc.):

``` sql
CREATE TABLE Producoes_Marvel (
    ID INT PRIMARY KEY AUTO_INCREMENT,
    Titulo VARCHAR(255) NOT NULL,
    Tipo VARCHAR(20),
    Ano INT,
    Estudio VARCHAR(100),
    Diretor_Criador VARCHAR(255),
    Classificacao VARCHAR(10),
    Conexao_MCU BOOLEAN,
    Sinopse TEXT,
    Duracao_Minutos INT,
    Qtd_Episodios INT
);
```

### 2. Execute o Script de Inserção

Carregue e execute o conteúdo do arquivo `marvel_sql_inserts.sql` para popular a tabela `Producoes_Marvel` com todos os registros listados neste repositório.

---

## 🤝 Contribuições

Contribuições são sempre bem-vindas!  
Se você encontrar algum erro, informação desatualizada ou tiver sugestões para novas produções, siga os passos:

```bash
# Faça um fork do projeto
# Crie uma branch para a sua alteração
git checkout -b feature/NovaProducao

# Faça suas alterações e commite
git commit -m "Adiciona NovaProducao"

# Envie para o seu repositório
git push origin feature/NovaProducao

# Abra um Pull Request

