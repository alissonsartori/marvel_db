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

```sql
-- Inserindo dados na tabela Producoes_Marvel

-- Pré-MCU e Universos Paralelos (Fox, Sony, etc.)
INSERT INTO Producoes_Marvel (Titulo, Tipo, Ano, Estudio, Diretor_Criador, Classificacao, Conexao_MCU, Sinopse, Duracao_Minutos, Qtd_Episodios) VALUES
('X-Men: O Filme', 'Filme', 2000, '20th Century Fox', 'Bryan Singer', '12', 0, 'Mutantes lutam por aceitação enquanto enfrentam uma ameaça que quer transformá-los.', 104, NULL),
('Homem-Aranha', 'Filme', 2002, 'Sony Pictures', 'Sam Raimi', 'Livre', 0, 'Um jovem picado por uma aranha radioativa ganha superpoderes e aprende sobre responsabilidade.', 121, NULL),
('X-Men 2', 'Filme', 2003, '20th Century Fox', 'Bryan Singer', '12', 0, 'Os X-Men se unem a seus inimigos para combater um militar que ameaça todos os mutantes.', 134, NULL),
('Hulk', 'Filme', 2003, 'Universal Pictures', 'Ang Lee', '12', 0, 'Um cientista se transforma em um monstro verde gigante sempre que fica com raiva.', 138, NULL),
('Homem-Aranha 2', 'Filme', 2004, 'Sony Pictures', 'Sam Raimi', 'Livre', 0, 'Peter Parker luta para equilibrar sua vida pessoal com os deveres de super-herói.', 127, NULL),
('Quarteto Fantástico', 'Filme', 2005, '20th Century Fox', 'Tim Story', 'Livre', 0, 'Quatro astronautas ganham superpoderes após serem expostos a radiação cósmica.', 106, NULL),
('X-Men: O Confronto Final', 'Filme', 2006, '20th Century Fox', 'Brett Ratner', '12', 0, 'Uma "cura" para a mutação divide a comunidade mutante e leva a uma batalha épica.', 104, NULL),
('Homem-Aranha 3', 'Filme', 2007, 'Sony Pictures', 'Sam Raimi', '12', 0, 'Peter Parker enfrenta novos vilões enquanto lida com um simbionte alienígena.', 139, NULL),
('Quarteto Fantástico e o Surfista Prateado', 'Filme', 2007, '20th Century Fox', 'Tim Story', 'Livre', 0, 'O Quarteto Fantástico enfrenta o arauto de uma entidade cósmica devoradora de mundos.', 92, NULL),
('X-Men Origens: Wolverine', 'Filme', 2009, '20th Century Fox', 'Gavin Hood', '14', 0, 'A história de origem de Wolverine, seu passado violento e sua relação com seu irmão.', 107, NULL),
('X-Men: Primeira Classe', 'Filme', 2011, '20th Century Fox', 'Matthew Vaughn', '12', 0, 'A história do início da amizade e rivalidade entre Charles Xavier e Erik Lehnsherr.', 131, NULL),
('O Espetacular Homem-Aranha', 'Filme', 2012, 'Sony Pictures', 'Marc Webb', '10', 0, 'Peter Parker descobre os segredos de seus pais enquanto aprende a ser um herói.', 136, NULL),
('Wolverine: Imortal', 'Filme', 2013, '20th Century Fox', 'James Mangold', '12', 0, 'Wolverine viaja para o Japão e enfrenta seus demônios internos e a Yakuza.', 126, NULL),
('X-Men: Dias de um Futuro Esquecido', 'Filme', 2014, '20th Century Fox', 'Bryan Singer', '12', 0, 'Os X-Men enviam Wolverine ao passado para mudar a história e evitar um futuro apocalíptico.', 132, NULL),
('O Espetacular Homem-Aranha 2: A Ameaça de Electro', 'Filme', 2014, 'Sony Pictures', 'Marc Webb', '12', 0, 'Homem-Aranha enfrenta novos inimigos enquanto tenta proteger seus entes queridos.', 142, NULL),
('Deadpool', 'Filme', 2016, '20th Century Fox', 'Tim Miller', '16', 0, 'Um mercenário tagarela ganha poderes de cura e busca vingança contra quem arruinou sua vida.', 108, NULL),
('X-Men: Apocalipse', 'Filme', 2016, '20th Century Fox', 'Bryan Singer', '12', 0, 'Os X-Men enfrentam o primeiro e mais poderoso mutante, Apocalipse.', 144, NULL),
('Logan', 'Filme', 2017, '20th Century Fox', 'James Mangold', '16', 0, 'Em um futuro sombrio, um Wolverine envelhecido protege uma jovem mutante com poderes semelhantes aos seus.', 137, NULL),
('Venom', 'Filme', 2018, 'Sony Pictures', 'Ruben Fleischer', '14', 0, 'Um jornalista se une a um simbionte alienígena para se tornar um anti-herói letal.', 112, NULL),
('X-Men: Fênix Negra', 'Filme', 2019, '20th Century Fox', 'Simon Kinberg', '12', 0, 'Jean Grey perde o controle de seus poderes, tornando-se uma ameaça para o universo.', 113, NULL),
('Venom: Tempo de Carnificina', 'Filme', 2021, 'Sony Pictures', 'Andy Serkis', '14', 0, 'Venom enfrenta um novo e caótico inimigo, o simbionte Carnificina.', 97, NULL),
('Morbius', 'Filme', 2022, 'Sony Pictures', 'Daniel Espinosa', '14', 0, 'Um bioquímico tenta se curar de uma rara doença sanguínea e se torna um tipo de vampiro.', 104, NULL),
('Madame Teia', 'Filme', 2024, 'Sony Pictures', 'S.J. Clarkson', '14', 0, 'Uma paramédica de Manhattan descobre que tem habilidades de clarividência.', 117, NULL);

-- Universo Cinematográfico Marvel (MCU) - Filmes
INSERT INTO Producoes_Marvel (Titulo, Tipo, Ano, Estudio, Diretor_Criador, Classificacao, Conexao_MCU, Sinopse, Duracao_Minutos, Qtd_Episodios) VALUES
('Homem de Ferro', 'Filme', 2008, 'Marvel Studios', 'Jon Favreau', '12', 1, 'Um industrial bilionário constrói uma armadura de alta tecnologia e se torna um super-herói.', 126, NULL),
('O Incrível Hulk', 'Filme', 2008, 'Marvel Studios', 'Louis Leterrier', '12', 1, 'Bruce Banner busca uma cura para sua condição enquanto é caçado pelo exército.', 112, NULL),
('Homem de Ferro 2', 'Filme', 2010, 'Marvel Studios', 'Jon Favreau', '12', 1, 'Tony Stark enfrenta a pressão do governo e um novo inimigo ligado ao passado de sua família.', 124, NULL),
('Thor', 'Filme', 2011, 'Marvel Studios', 'Kenneth Branagh', '10', 1, 'O poderoso, mas arrogante, deus do trovão é banido de Asgard para a Terra.', 115, NULL),
('Capitão América: O Primeiro Vingador', 'Filme', 2011, 'Marvel Studios', 'Joe Johnston', '10', 1, 'Um jovem franzino se torna um super-soldado durante a Segunda Guerra Mundial.', 124, NULL),
('Os Vingadores', 'Filme', 2012, 'Marvel Studios', 'Joss Whedon', '12', 1, 'Os maiores heróis da Terra se unem para impedir que Loki e seu exército alienígena dominem o mundo.', 143, NULL),
('Homem de Ferro 3', 'Filme', 2013, 'Marvel Studios', 'Shane Black', '12', 1, 'Tony Stark enfrenta um terrorista conhecido como o Mandarim.', 130, NULL),
('Thor: O Mundo Sombrio', 'Filme', 2013, 'Marvel Studios', 'Alan Taylor', '12', 1, 'Thor se une a Loki para salvar os Nove Reinos de um antigo inimigo.', 112, NULL),
('Capitão América: O Soldado Invernal', 'Filme', 2014, 'Marvel Studios', 'Anthony & Joe Russo', '12', 1, 'Capitão América descobre uma conspiração dentro da S.H.I.E.L.D. e enfrenta um assassino misterioso.', 136, NULL),
('Guardiões da Galáxia', 'Filme', 2014, 'Marvel Studios', 'James Gunn', '12', 1, 'Um grupo de desajustados intergalácticos se une para proteger um poderoso artefato.', 121, NULL),
('Vingadores: Era de Ultron', 'Filme', 2015, 'Marvel Studios', 'Joss Whedon', '12', 1, 'Os Vingadores enfrentam Ultron, uma inteligência artificial que ameaça a humanidade.', 141, NULL),
('Homem-Formiga', 'Filme', 2015, 'Marvel Studios', 'Peyton Reed', '12', 1, 'Um ladrão adquire um traje que lhe permite encolher em escala e aumentar em força.', 117, NULL),
('Capitão América: Guerra Civil', 'Filme', 2016, 'Marvel Studios', 'Anthony & Joe Russo', '12', 1, 'Uma divisão ideológica entre os Vingadores os coloca uns contra os outros.', 147, NULL),
('Doutor Estranho', 'Filme', 2016, 'Marvel Studios', 'Scott Derrickson', '12', 1, 'Um neurocirurgião descobre o mundo oculto da magia e das dimensões alternativas.', 115, NULL),
('Guardiões da Galáxia Vol. 2', 'Filme', 2017, 'Marvel Studios', 'James Gunn', '12', 1, 'Os Guardiões desvendam o mistério da verdadeira filiação de Peter Quill.', 136, NULL),
('Homem-Aranha: De Volta ao Lar', 'Filme', 2017, 'Marvel Studios', 'Jon Watts', '12', 1, 'Peter Parker tenta equilibrar a vida de estudante com seus deveres de super-herói.', 133, NULL),
('Thor: Ragnarok', 'Filme', 2017, 'Marvel Studios', 'Taika Waititi', '12', 1, 'Thor se encontra preso em um planeta e precisa correr contra o tempo para impedir o Ragnarok.', 130, NULL),
('Pantera Negra', 'Filme', 2018, 'Marvel Studios', 'Ryan Coogler', '14', 1, 'T''Challa retorna a Wakanda para assumir o trono, mas é desafiado por um antigo inimigo.', 134, NULL),
('Vingadores: Guerra Infinita', 'Filme', 2018, 'Marvel Studios', 'Anthony & Joe Russo', '12', 1, 'Os Vingadores e seus aliados tentam impedir o titã Thanos de coletar as Joias do Infinito.', 149, NULL),
('Homem-Formiga e a Vespa', 'Filme', 2018, 'Marvel Studios', 'Peyton Reed', '12', 1, 'Scott Lang se une a Hope van Dyne em uma missão urgente no Reino Quântico.', 118, NULL),
('Capitã Marvel', 'Filme', 2019, 'Marvel Studios', 'Anna Boden & Ryan Fleck', '12', 1, 'Uma piloto da Força Aérea se torna uma das heroínas mais poderosas do universo.', 123, NULL),
('Vingadores: Ultimato', 'Filme', 2019, 'Marvel Studios', 'Anthony & Joe Russo', '12', 1, 'Após os eventos devastadores de Guerra Infinita, os Vingadores se reúnem para uma última cartada.', 181, NULL),
('Homem-Aranha: Longe de Casa', 'Filme', 2019, 'Marvel Studios', 'Jon Watts', '12', 1, 'Peter Parker vai de férias para a Europa, mas é convocado para combater uma nova ameaça.', 129, NULL),
('Viúva Negra', 'Filme', 2021, 'Marvel Studios', 'Cate Shortland', '14', 1, 'Natasha Romanoff confronta seu passado e uma conspiração perigosa.', 134, NULL),
('Shang-Chi e a Lenda dos Dez Anéis', 'Filme', 2021, 'Marvel Studios', 'Destin Daniel Cretton', '14', 1, 'Shang-Chi é forçado a confrontar o passado que ele pensou ter deixado para trás.', 132, NULL),
('Eternos', 'Filme', 2021, 'Marvel Studios', 'Chloé Zhao', '14', 1, 'Uma raça de seres imortais se reúne para proteger a humanidade de seus antigos inimigos.', 156, NULL),
('Homem-Aranha: Sem Volta para Casa', 'Filme', 2021, 'Marvel Studios', 'Jon Watts', '12', 1, 'A identidade do Homem-Aranha é revelada, e ele busca a ajuda do Doutor Estranho.', 148, NULL),
('Doutor Estranho no Multiverso da Loucura', 'Filme', 2022, 'Marvel Studios', 'Sam Raimi', '14', 1, 'Doutor Estranho atravessa as perigosas realidades alternativas do Multiverso.', 126, NULL),
('Thor: Amor e Trovão', 'Filme', 2022, 'Marvel Studios', 'Taika Waititi', '14', 1, 'Thor busca a paz interior, mas precisa retornar à ação para enfrentar o Carniceiro dos Deuses.', 118, NULL),
('Pantera Negra: Wakanda Para Sempre', 'Filme', 2022, 'Marvel Studios', 'Ryan Coogler', '14', 1, 'Os líderes de Wakanda lutam para proteger sua nação após a morte do Rei T''Challa.', 161, NULL),
('Homem-Formiga e a Vespa: Quantumania', 'Filme', 2023, 'Marvel Studios', 'Peyton Reed', '12', 1, 'Os heróis exploram o Reino Quântico e encontram Kang, o Conquistador.', 124, NULL),
('Guardiões da Galáxia Vol. 3', 'Filme', 2023, 'Marvel Studios', 'James Gunn', '14', 1, 'Os Guardiões embarcam em uma missão para salvar a vida de Rocket.', 150, NULL),
('As Marvels', 'Filme', 2023, 'Marvel Studios', 'Nia DaCosta', '12', 1, 'Os poderes de Carol Danvers, Kamala Khan e Monica Rambeau se entrelaçam.', 105, NULL);

-- Universo Cinematográfico Marvel (MCU) - Séries Disney+
INSERT INTO Producoes_Marvel (Titulo, Tipo, Ano, Estudio, Diretor_Criador, Classificacao, Conexao_MCU, Sinopse, Duracao_Minutos, Qtd_Episodios) VALUES
('WandaVision', 'Série', 2021, 'Marvel Studios', 'Jac Schaeffer', '12', 1, 'Wanda Maximoff e Visão vivem uma vida suburbana ideal, mas começam a suspeitar que nem tudo é o que parece.', NULL, 9),
('Falcão e o Soldado Invernal', 'Série', 2021, 'Marvel Studios', 'Malcolm Spellman', '14', 1, 'Sam Wilson e Bucky Barnes se unem em uma aventura global que testa suas habilidades e paciência.', NULL, 6),
('Loki', 'Série', 2021, 'Marvel Studios', 'Michael Waldron', '12', 1, 'A versão de Loki que escapou em "Vingadores: Ultimato" é capturada pela Autoridade de Variação Temporal.', NULL, 12),
('Gavião Arqueiro', 'Série', 2021, 'Marvel Studios', 'Jonathan Igla', '12', 1, 'Clint Barton se une a uma jovem arqueira, Kate Bishop, para confrontar inimigos de seu passado.', NULL, 6),
('Cavaleiro da Lua', 'Série', 2022, 'Marvel Studios', 'Jeremy Slater', '16', 1, 'Um homem com transtorno dissociativo de identidade descobre que tem os poderes de um deus egípcio da lua.', NULL, 6),
('Ms. Marvel', 'Série', 2022, 'Marvel Studios', 'Bisha K. Ali', '10', 1, 'Uma fã de super-heróis de Nova Jersey ganha seus próprios superpoderes.', NULL, 6),
('Mulher-Hulk: Defensora de Heróis', 'Série', 2022, 'Marvel Studios', 'Jessica Gao', '14', 1, 'Uma advogada que se especializa em casos sobre-humanos também precisa lidar com seus próprios poderes.', NULL, 9),
('Invasão Secreta', 'Série', 2023, 'Marvel Studios', 'Kyle Bradstreet', '14', 1, 'Nick Fury descobre uma facção de Skrulls que planeja assumir o controle da Terra.', NULL, 6),
('Echo', 'Série', 2024, 'Marvel Studios', 'Marion Dayre', '16', 1, 'Maya Lopez é perseguida pelo império do crime de Wilson Fisk e deve confrontar seu passado.', NULL, 5);

-- Animações Relevantes
INSERT INTO Producoes_Marvel (Titulo, Tipo, Ano, Estudio, Diretor_Criador, Classificacao, Conexao_MCU, Sinopse, Duracao_Minutos, Qtd_Episodios) VALUES
('X-Men: Evolution', 'Animação', 2000, 'Marvel Enterprises', 'Boyd Kirkland', 'Livre', 0, 'Versão adolescente dos X-Men que equilibram a vida no colégio com o heroísmo.', NULL, 52),
('Homem-Aranha: A Série Animada (2003)', 'Animação', 2003, 'Mainframe Entertainment', 'Brian Michael Bendis', '10', 0, 'Continuação do primeiro filme de Sam Raimi em animação CGI.', NULL, 13),
('O Espetacular Homem-Aranha', 'Animação', 2008, 'Sony Pictures Television', 'Greg Weisman', '10', 0, 'Peter Parker lida com o colégio, amizades e uma galeria crescente de vilões.', NULL, 26),
('Vingadores: Os Heróis Mais Poderosos da Terra', 'Animação', 2010, 'Marvel Animation', 'Ciro Nieli', '10', 0, 'Uma aclamada série que reúne a equipe clássica dos Vingadores.', NULL, 52),
('What If...?', 'Animação', 2021, 'Marvel Studios', 'A.C. Bradley', '12', 1, 'O Vigia explora linhas do tempo alternativas no multiverso, mostrando o que aconteceria se momentos cruciais do MCU ocorressem de forma diferente.', NULL, 18),
('Homem-Aranha no Aranhaverso', 'Animação', 2018, 'Sony Pictures Animation', 'Bob Persichetti', '10', 0, 'Miles Morales se torna o Homem-Aranha de sua realidade e se une a outras versões do herói de outras dimensões.', 117, NULL),
('Homem-Aranha: Através do Aranhaverso', 'Animação', 2023, 'Sony Pictures Animation', 'Joaquim Dos Santos', '10', 0, 'Miles Morales é catapultado através do Multiverso, onde encontra uma equipe de Pessoas-Aranha.', 140, NULL),
('X-Men ''97', 'Animação', 2024, 'Marvel Studios', 'Beau DeMayo', '12', 0, 'Continuação da icônica série animada dos X-Men dos anos 90.', NULL, 10);

-- Próximos Lançamentos (Dados podem mudar)
INSERT INTO Producoes_Marvel (Titulo, Tipo, Ano, Estudio, Diretor_Criador, Classificacao, Conexao_MCU, Sinopse, Duracao_Minutos, Qtd_Episodios) VALUES
('Deadpool & Wolverine', 'Filme', 2024, 'Marvel Studios', 'Shawn Levy', '16', 1, 'Wolverine se recupera de seus ferimentos quando cruza o caminho do mercenário tagarela, Deadpool.', NULL, NULL),
('Agatha: All Along', 'Série', 2024, 'Marvel Studios', 'Jac Schaeffer', '14', 1, 'Agatha Harkness finalmente se liberta de um feitiço e busca recuperar seus antigos poderes.', NULL, 9),
('Kraven, o Caçador', 'Filme', 2024, 'Sony Pictures', 'J.C. Chandor', '16', 0, 'A história de origem de um dos vilões mais icônicos do Homem-Aranha.', NULL, NULL),
('Your Friendly Neighborhood Spider-Man', 'Animação', 2024, 'Marvel Studios', 'Jeff Trammell', '10', 1, 'Uma série animada que segue Peter Parker em seu caminho para se tornar o Homem-Aranha no MCU.', NULL, NULL),
('Capitão América: Admirável Mundo Novo', 'Filme', 2025, 'Marvel Studios', 'Julius Onah', NULL, 1, 'Sam Wilson assume totalmente o manto do Capitão América.', NULL, NULL),
('Daredevil: Born Again', 'Série', 2025, 'Marvel Studios', 'Dario Scardapane', '16', 1, 'Matt Murdock e Wilson Fisk tentam deixar seus alter egos para trás, mas o passado os alcança.', NULL, 9),
('Thunderbolts*', 'Filme', 2025, 'Marvel Studios', 'Jake Schreier', NULL, 1, 'Um grupo de anti-heróis e vilões reformados é enviado em missões pelo governo.', NULL, NULL),
('Quarteto Fantástico', 'Filme', 2025, 'Marvel Studios', 'Matt Shakman', NULL, 1, 'A introdução da primeira família da Marvel no Universo Cinematográfico Marvel.', NULL, NULL);
```

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

