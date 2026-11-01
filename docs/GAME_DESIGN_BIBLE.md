# Biscoito & Mingau: A Relíquia da Floresta — Bíblia Oficial do Jogo

## 1. Visão geral

**Biscoito & Mingau: A Relíquia da Floresta** é um platformer 2D de precisão, momentum, exploração e replay, com dois protagonistas jogáveis que atravessam a mesma aventura de maneiras diferentes.

O jogo deve ser tratado como videogame desde o início, não como site nem como experiência presa a navegador.

### Pilares oficiais

- Engine: **Cocos Creator 3.x**
- Linguagem: **TypeScript**
- Angular no runtime: **não**
- Visual: **pixel art moderna, colorida, expressiva e legível**
- FPS alvo: **60 FPS estáveis**
- Plataforma principal: **Windows nativo instalável**
- Segunda plataforma: **Android**
- Web: **demo, QA, protótipo e showcase**
- Possível futuro: **Steam**
- Gamepad: **requisito desde o protótipo**
- Suporte prioritário: **Xbox e DualSense/PS5**
- Estrutura: **mesmas fases para os dois personagens**
- Escolha do personagem: **antes de cada fase**
- Troca instantânea durante fase: **não**
- Replay com outro personagem: **sim**
- RPG/skill tree: **não**
- Combate: **secundário**
- Prioridade absoluta: **movimento**
- Backend: **futuro, separado do runtime, sem bloquear campanha offline**

> Uma aventura. Dois protagonistas. Dois estilos de movimento.

---

# 2. História oficial

Biscoito e Mingau vivem em **Vila Folhaverde**, uma pequena comunidade cercada por uma floresta antiga.

Eles cresceram próximos, mas transformam praticamente tudo em competição.

Biscoito é impulsivo, brincalhão e confiante demais. Mingau é observador, preciso e adora provar que pensou melhor.

Durante a tradicional **Festa das Lanternas da Floresta**, a comunidade apresenta sua relíquia mais importante: o **Coração da Floresta**.

A relíquia mantém antigas rotas, nascentes, mecanismos e passagens em equilíbrio.

No meio da celebração, a relíquia é roubada por **Risco, o Quati Explorador**.

Risco acredita que o Coração da Floresta é a chave para abrir uma antiga câmara escondida no centro da região e revelar um tesouro lendário.

Ele não se considera um vilão. É aventureiro, convencido e obcecado por provar que fez a maior descoberta da história local.

Ao remover a relíquia do seu lugar:

- antigos guardiões despertam;
- caminhos começam a se alterar;
- mecanismos esquecidos voltam a funcionar;
- criaturas passam a agir de maneira estranha;
- regiões inteiras ficam instáveis.

Biscoito e Mingau veem Risco fugir e partem atrás dele, cada um convencido de que será o responsável por recuperar a relíquia primeiro.

No início, a rivalidade atrapalha.

No meio da campanha, os dois percebem que existem situações em que a abordagem do outro funciona melhor.

No final, continuam competitivos, mas já existe respeito real entre eles.

A rivalidade saudável deve continuar existindo porque faz parte da identidade da franquia.

A história precisa ser entendida mesmo por quem pula diálogos.

Priorizar:

- animações;
- cenário;
- expressões;
- pequenos diálogos;
- humor visual;
- eventos durante a própria fase.

Evitar:

- caixas de texto longas;
- lore obrigatório;
- história pesada;
- violência gráfica;
- múltiplas campanhas separadas.

---

# 3. Protagonistas

## 3.1 Biscoito — cachorro

Personalidade:

- impulsivo;
- brincalhão;
- competitivo;
- leal;
- confiante demais;
- entra primeiro e pensa depois.

Pilar mecânico: **momentum horizontal**.

Habilidades:

- corrida progressiva;
- aceleração por terreno;
- salto longo quando há momentum;
- impulso em rampas;
- dash rasteiro curto;
- atravessar obstáculos frágeis marcados;
- farejar alguns segredos;
- impacto lateral em inimigos vulneráveis quando estiver em velocidade adequada.

Biscoito NÃO deve virar Sonic.

Proibido como identidade principal:

- spin dash;
- loops obrigatórios;
- velocidade extrema constante;
- copiar física ou leitura visual de Sonic.

## 3.2 Mingau — gato

Personalidade:

- observador;
- preciso;
- irônico;
- competitivo;
- curioso;
- pensa antes de agir.

Pilar mecânico: **mobilidade vertical**.

Habilidades:

- wall jump;
- corrida curta na parede;
- agarrar redes e superfícies específicas;
- equilíbrio em cabos;
- passagens estreitas;
- controle aéreo mais técnico;
- pounce/bounce ofensivo vindo de cima ou em diagonal.

Mingau não pode ser apenas “o personagem que pula mais alto”.

A diferença precisa vir de como ele combina parede, borda, cabo e precisão.

---

# 4. Física compartilhada

A física base deve ser muito próxima entre os dois para impedir que o projeto vire duas campanhas diferentes.

Compartilhar:

- gravidade;
- altura básica de salto;
- velocidade base compatível;
- hitboxes próximas;
- coyote time;
- jump buffer;
- aceleração;
- desaceleração;
- controle no ar;
- aterrissagem responsiva.

A habilidade exclusiva nunca pode tornar a rota principal impossível para o outro personagem.

---

# 5. Filosofia das fases

A fase é uma só.

Exemplo:

```text
                    MINGAU
             parede ┃
                    ┃═══ segredo
                    ┃
───────        ─────┘

BISCOITO → → → RAMPA → salto longo → segredo
```

Os dois chegam ao mesmo destino.

Mingau resolve verticalmente.
Biscoito resolve por velocidade, terreno e momentum.

## Regra 80/20

Aproximadamente:

- 80% da fase compartilhada;
- até 20% com atalhos, segredos ou soluções que favorecem um deles.

Nunca criar duas fases completas escondidas dentro da mesma fase.

---

# 6. Escolha do personagem e replay

Antes de cada fase:

**ESCOLHA QUEM VAI ENTRAR**

- Biscoito
- Mingau

Não existe troca instantânea durante gameplay normal.

Ao terminar a fase registrar separadamente:

- tempo de Biscoito;
- tempo de Mingau;
- Emblemas;
- Fragmentos;
- medalha;
- melhor tempo.

Exemplo:

```text
TEMPO
BISCOITO   01:38.920
MINGAU     01:42.381

MELHOR TEMPO: BISCOITO
```

O objetivo é fazer o jogador pensar naturalmente:

> Agora quero tentar com o outro.

---

# 7. Coletáveis

Poucos tipos.

## Fragmentos

Coletável comum e opcional.

Não funciona como moeda de grind.

## Emblemas

3 secretos por fase normal.

Devem premiar:

- exploração;
- domínio do movimento;
- atalhos;
- soluções alternativas.

## Medalha de tempo

- Bronze
- Prata
- Ouro

Os tempos só devem ser fechados depois de playtests reais.

Tela de fase:

```text
✓ Concluída
◆◆◇ 2/3 Emblemas
🥈 Prata
🐕 Biscoito: concluída
🐈 Mingau: não concluída
```

---

# 8. Combate

O jogo TERÁ inimigos.

Não será apenas puzzle.

Mas também não será um jogo de combate com plataformas.

Regra oficial:

**MOVIMENTO > LEVEL DESIGN > INIMIGOS > COMBATE**

Não haverá:

- espada;
- arma de fogo;
- combo tradicional;
- árvore de armas;
- loot;
- raridade;
- RPG.

Os inimigos devem fazer parte do movimento.

## Ataque universal — Bounce

Ao cair corretamente sobre inimigos vulneráveis:

1. inimigo recebe dano ou é derrotado;
2. personagem recebe pequeno impulso vertical;
3. movimento continua.

Esse bounce pode fazer parte de rotas rápidas.

## Biscoito — Impacto de Momentum

Com velocidade suficiente:

- acerta certos inimigos lateralmente;
- quebra obstáculos frágeis;
- mantém parte do momentum após impacto.

Não existe botão de soco.

## Mingau — Pounce

Mingau transforma salto/queda direcionada em ataque de precisão.

Pode:

- atingir por cima;
- atingir diagonalmente;
- ricochetear após impacto;
- combinar parede + salto + pounce.

---

# 9. Gancho

Não haverá Grappling Hook permanente para Biscoito ou Mingau.

Isso aproximaria demais a identidade do jogo de Grapple Dog.

Haverá elementos ambientais de balanço:

- cipós;
- cordas;
- argolas;
- cabos;
- galhos flexíveis;
- mecanismos pendulares.

Esses elementos pertencem ao cenário.

**Balanço ambiental: SIM.**
**Gancho equipado pelos protagonistas: NÃO.**

Risco poderá utilizar uma garra/corda como ferramenta própria no boss final, porque isso faz parte da identidade dele e não dos protagonistas.

---

# 10. Inimigos comuns

## 10.1 Broto Andante

Função: inimigo terrestre básico.

Comportamento:

- patrulha área curta;
- vira na borda;
- contato causa dano.

Derrota:

- bounce;
- impacto de Biscoito;
- pounce de Mingau.

Vida: 1 acerto.

## 10.2 Pula-Espinho

Função: ensinar timing.

Comportamento:

- alterna postura segura e salto perigoso;
- espinhos ficam expostos durante parte da animação.

Derrota:

- esperar janela vulnerável;
- atacar após aterrissagem;
- também pode ser ignorado.

## 10.3 Besouro Cascudo

Função: mudar abordagem.

Comportamento:

- armadura frontal;
- avanço lento;
- reage à aproximação.

Derrota:

- por cima;
- por trás;
- Biscoito quebra guarda com momentum;
- Mingau usa altura para reposicionar.

## 10.4 Mariposa de Bruma

Função: ameaça aérea.

Comportamento:

- patrulha curva simples;
- mergulha ao detectar jogador;
- pode servir de bounce em rota avançada.

## 10.5 Flor Estaladora

Função: projétil e ritmo.

Comportamento:

- abre;
- sinaliza;
- dispara semente;
- fecha.

Só fica vulnerável na abertura.

## 10.6 Rolador de Musgo

Função: obstáculo móvel.

Comportamento:

- enrola;
- desce inclinações;
- ganha velocidade;
- pode quebrar barreiras.

Não precisa ser derrotado.

## 10.7 Sentinela de Pedra

Inimigo avançado.

- 2 interações para derrotar;
- ataque claramente telegráfico;
- bloqueia temporariamente uma rota;
- nunca vira esponja de vida.

## 10.8 Corredor Corrompido

- persegue jogador em trecho curto;
- cria mini corrida;
- pode ser despistado usando terreno.

## 10.9 Vespa-Lanterna

- inimigo aéreo;
- projétil simples;
- obriga mudança de altura;
- pouca vida.

---

# 11. Elites e mini-bosses

Não haverá sistema de “capitães”.

Não queremos estrutura de RPG com:

- comum;
- raro;
- elite;
- capitão;
- lendário.

Podem existir **Encontros de Elite** a partir do Mundo 2.

Regras:

- no máximo 1 em algumas fases;
- 20–40 segundos;
- sem barra de vida;
- normalmente uma versão avançada de inimigo existente;
- foco em desafio de movimento.

Não haverá mini-boss obrigatório em toda fase.

---

# 12. Bosses

**1 boss por mundo.**

Total:

- 5 mundos;
- 4 fases normais por mundo;
- 1 boss por mundo;
- **5 bosses**.

Boss deve ser evento especial.

Boss normal:

- 3–5 minutos na primeira vitória;
- poucos padrões fortes;
- telegraph claro;
- arena faz parte do desafio;
- pouca repetição;
- sem barra de vida enorme.

Boss final:

- 6–8 minutos;
- múltiplas etapas;
- testar tudo que foi aprendido.

---

# 13. Boss 1 — Javali de Pedra

Arena:

- vale;
- pequenas rampas;
- paredes laterais;
- três pilares antigos.

Padrão A — Investida:

- prepara;
- raspa a pata;
- corre horizontalmente.

Se bater no pilar, fica vulnerável.

Padrão B — Pisão:

- salta;
- cai;
- gera onda rasteira.

Padrão C — Rochas:

- bate no chão;
- pedras caem com telegraph.

Três janelas corretas encerram a luta.

Duração: 3–4 min.

---

# 14. Boss 2 — Coruja dos Vendavais

Arena:

- plataformas suspensas;
- correntes de ar.

Padrões:

- mergulho diagonal;
- rajada horizontal;
- penas lentas;
- troca de plataforma.

O jogador usa vento e plataformas para alcançar a janela vulnerável.

Duração: 3–5 min.

---

# 15. Boss 3 — Serpente da Correnteza

Arena:

- água sobe e desce;
- pedras;
- plataformas temporárias.

Padrões:

- emerge em pontos telegráficos;
- cria onda;
- atravessa arena;
- quebra plataformas.

O jogador induz a serpente a atingir mecanismos antigos antes de poder atacá-la.

Duração: 4–5 min.

---

# 16. Boss 4 — Vigia das Ruínas

Visual:

- autômato antigo de pedra e raízes.

Arena:

- estrutura vertical em três níveis.

Padrões:

- braço horizontal;
- queda de blocos;
- energia da relíquia;
- alteração da geometria da arena.

O jogador ativa três mecanismos e abre o núcleo.

Não é batalha de DPS.

Duração: 4–5 min.

---

# 17. Boss final — Risco e o Coração da Floresta

Local: **Santuário do Coração**.

Duração alvo: **6–8 minutos**.

## Fase 1 — A Última Corrida

Risco foge pelo santuário com a relíquia.

Gameplay:

- perseguição;
- plataformas móveis;
- obstáculos dos mundos anteriores;
- rotas alternativas.

Biscoito:

- ganha terreno usando momentum.

Mingau:

- corta caminho verticalmente.

Não existe dano tradicional nessa etapa.

Objetivo: alcançar Risco.

## Fase 2 — Ferramentas de Explorador

Risco usa:

- bomba de sementes;
- garra/corda;
- dash entre plataformas;
- lançamento de artefatos;
- armadilhas no chão.

Janela de vulnerabilidade:

Risco prende a garra em mecanismo pesado ou colide após o jogador evitar a investida.

Três janelas encerram a etapa.

## Fase 3 — Relíquia Fora de Controle

Risco tenta ativar o Coração.

A relíquia cria:

- plataformas temporárias;
- raízes gigantes;
- ondas de energia;
- blocos móveis;
- mudanças de altura.

Objetivo:

ativar 3 selos ao redor da arena.

Biscoito usa rampas e momentum.
Mingau usa paredes, cabos e verticalidade.

## Fase 4 — Último Contra-Ataque

Sequência final:

1. Risco inicia investida final;
2. jogador desvia;
3. Risco perde equilíbrio;
4. relíquia se solta;
5. jogador precisa alcançar o Coração antes que ele caia no abismo.

O final é um desafio de plataforma, não um golpe final tradicional.

Risco não morre.

Ele percebe o tamanho do problema que causou.

---

# 18. Final

Biscoito e Mingau retornam para Vila Folhaverde.

O Coração da Floresta volta ao seu lugar.

A Festa das Lanternas é retomada.

Quando alguém pergunta:

> Quem recuperou a relíquia?

Biscoito e Mingau apontam para si mesmos ao mesmo tempo.

Os dois começam outra discussão.

Corta para os créditos.

A rivalidade continua.

---

# 19. Estrutura da campanha

A campanha possui **5 mundos × 5 fases = 25 fases principais**.

Cada mundo:

- Fase 1: introdução do bioma/ideia;
- Fase 2: desenvolvimento;
- Fase 3: combinação;
- Fase 4: prova de domínio;
- Fase 5: boss.

## Mundo 1 — Bosque de Folhaverde

Tema: floresta ensolarada, vila, trilhas, madeira, riachos e festa interrompida.

### 1-1 — Trilhas da Festa

Tutorial real.

Ensina:

- correr;
- pular;
- coyote time;
- coletáveis;
- checkpoint;
- habilidade principal do personagem escolhido.

Obstáculos:

- troncos;
- buracos curtos;
- plataformas de madeira;
- declives;
- primeiro inimigo.

Segredo principal acessível por:

- parede com Mingau;
- rampa com Biscoito.

Duração: **4–5 min**.

### 1-2 — Ponte das Folhas

Tema:

- pontes;
- copas baixas;
- rios.

Novidades:

- plataformas móveis;
- cordas;
- galhos;
- água como risco leve.

Duração: **5–6 min**.

### 1-3 — Moinho do Riacho

Tema:

- moinho;
- mecanismos movidos por água.

Novidades:

- rodas;
- plataformas rotativas;
- jatos d'água;
- timing.

Duração: **5–6 min**.

### 1-4 — Corrida até o Desfiladeiro

Primeira fase realmente rápida.

Mistura:

- rampas;
- paredes;
- plataformas que caem;
- inimigos em movimento;
- perseguição a Risco.

Duração: **6–7 min**.

### 1-5 — Javali de Pedra

Duração: **3–4 min**.

---

## Mundo 2 — Copas do Vento

Tema:

- floresta alta;
- copas gigantes;
- cordas;
- vento;
- altitude.

Pilar: verticalidade + momentum aéreo.

### 2-1 — Subida dos Cipós

- paredes naturais;
- cipós;
- correntes de ar;
- plataformas estreitas.

Duração: **5–6 min**.

### 2-2 — Galhos em Movimento

- galhos balançando;
- plataformas temporárias;
- ninhos;
- vento lateral.

Duração: **5–7 min**.

### 2-3 — Tempestade nas Copas

- chuva;
- rajadas;
- superfícies escorregadias;
- leitura reduzida sem esconder perigo.

Duração: **6–7 min**.

### 2-4 — O Grande Salto

Fase de sequências longas de movimento.

Biscoito: momentum acumulado.
Mingau: parede + cabo + salto.

Duração: **6–8 min**.

### 2-5 — Coruja dos Vendavais

Duração: **3–5 min**.

---

## Mundo 3 — Garganta das Águas

Tema:

- cânions;
- cachoeiras;
- cavernas;
- canais antigos.

Pilar: fluxo, água e superfícies móveis.

### 3-1 — Pedras do Rio

- pedras móveis;
- correnteza;
- troncos;
- saltos curtos.

Duração: **5–7 min**.

### 3-2 — Cavernas de Cristal

- áreas verticais;
- plataformas por luz/eco;
- passagens estreitas;
- pedras frágeis.

Duração: **6–7 min**.

### 3-3 — Corredeira Selvagem

Trechos de alta velocidade.

Duração: **6–8 min**.

### 3-4 — Barragem Antiga

Mais puzzle sem abandonar movimento.

- comportas;
- rodas;
- mudanças do nível da água;
- rotas temporárias.

Duração: **7–8 min**.

### 3-5 — Serpente da Correnteza

Duração: **4–5 min**.

---

## Mundo 4 — Ruínas do Musgo

Tema:

- ruínas antigas;
- floresta tomando estruturas;
- mecanismos.

Pilar: precisão e rotas secretas.

### 4-1 — Portões Esquecidos

- portas temporizadas;
- blocos;
- plataformas antigas;
- mecanismos ligados à relíquia.

Duração: **6–7 min**.

### 4-2 — Jardim das Estátuas

- estátuas móveis;
- plataformas falsas legíveis;
- rotas de exploração.

Duração: **6–8 min**.

### 4-3 — Torre Partida

Fase majoritariamente vertical.

Biscoito também deve possuir uma rota divertida baseada em rampas internas, contrapesos e plataformas ascendentes.

Duração: **7–8 min**.

### 4-4 — Noite das Lanternas

Retoma elementos visuais da festa inicial em versão misteriosa.

- noite;
- iluminação;
- perseguição;
- mistura de mecânicas anteriores.

Duração: **7–9 min**.

### 4-5 — Vigia das Ruínas

Duração: **4–5 min**.

---

## Mundo 5 — Coração da Floresta

Tema:

- centro mágico da floresta;
- natureza + estruturas antigas fundidas.

Pilar: domínio de tudo aprendido.

### 5-1 — Caminhos Impossíveis

- plataformas surgem;
- paredes movem;
- atalhos temporários.

Duração: **6–8 min**.

### 5-2 — Raízes Profundas

Descida rápida seguida de subida técnica.

Duração: **7–8 min**.

### 5-3 — Ecos da Rivalidade

Fase construída especificamente para mostrar como Biscoito e Mingau resolvem os mesmos desafios de maneiras diferentes.

Duração: **7–9 min**.

### 5-4 — A Última Perseguição

Sem nova mecânica.

Exame final:

- rampas;
- paredes;
- água;
- vento;
- plataformas móveis;
- inimigos;
- atalhos;
- precisão.

Duração: **8–10 min**.

### 5-5 — Risco e o Coração da Floresta

Duração: **6–8 min**.

---

# 20. Ritmo interno de fase

Exemplo de fase de 6 minutos:

```text
0:00–0:45   entrada + leitura da mecânica
0:45–2:00   movimento principal
2:00–2:30   pequena variação / segredo
2:30–4:00   combinação com inimigos
4:00–5:15   trecho de domínio / velocidade
5:15–6:00   clímax + saída
```

Alternar:

**movimento → leitura → risco → recompensa → movimento**

Nunca manter intensidade máxima do início ao fim.

---

# 21. Puzzles

Terá puzzles curtos.

Tipos permitidos:

- ativar mecanismos;
- redirecionar objeto;
- alterar nível de água;
- abrir caminho temporário;
- usar inimigo/objeto para quebrar barreira;
- escolher rota;
- mecanismos com timing.

Duração ideal: **10–40 segundos**.

Não transformar o jogo em puzzle parado.

Distribuição conceitual:

- 60–70% plataforma/movimento;
- 15–20% inimigos/risco dinâmico;
- 10–15% exploração/segredos;
- 5–10% puzzles/contexto.

---

# 22. Checkpoints, vida e falha

Direção inicial:

- 3 pontos de vida;
- dano comum remove 1;
- perigo fatal reposiciona no checkpoint e remove vida;
- reinício rápido;
- sem sistema de vidas limitado estilo arcade.

Checkpoint deve fazer parte do mundo.

Possíveis formatos:

- lanternas;
- marcos de trilha;
- placas;
- totens;
- flores luminosas.

---

# 23. Direção visual

Pixel art moderna.

Não usar restrição rígida de 8-bit.

Objetivos:

- cores fortes;
- silhuetas legíveis;
- backgrounds em camadas;
- parallax discreto;
- plataformas claras;
- inimigos e perigos destacados;
- personagens pequenos, mas expressivos.

Não usar vetor como arte final.

Evitar:

- luvas brancas genéricas;
- tênis exagerados;
- estética “mascote radical anos 90” copiada;
- proporções de Sonic.

### Biscoito

- corpo mais arredondado;
- poses inclinadas quando ganha velocidade;
- orelhas/cauda comunicam momentum.

### Mingau

- silhueta mais alongada;
- cauda comunica equilíbrio;
- poses claras de parede, salto e aterrissagem.

Animações mínimas para ambos:

- idle;
- idle longo;
- corrida;
- aceleração;
- frenagem;
- salto;
- ápice;
- queda;
- aterrissagem;
- hit;
- falha;
- interação;
- comemoração.

Extras de Biscoito:

- impulso;
- dash rasteiro;
- salto longo;
- farejar.

Extras de Mingau:

- wall cling;
- wall jump;
- wall run;
- equilíbrio;
- passagem estreita.

---

# 24. Resolução e tela

O produto principal será um jogo instalável no PC.

Não deve parecer um canvas dentro de uma página.

Resolução lógica inicial recomendada:

**640×360 — 16:9**

Escalar proporcionalmente para:

- 1080p;
- 1440p;
- 4K;
- resoluções mobile.

Nunca esticar X e Y de forma independente.

Modos Windows:

- Fullscreen;
- Borderless;
- Janela.

Configurações:

- resolução;
- VSync;
- música;
- SFX;
- vibração;
- controles;
- efeitos visuais.

---

# 25. Controles

## PC — teclado

- WASD/setas;
- Space / botão de pulo configurável;
- Ability;
- Interact;
- Pause.

## Gamepad

Gamepad é requisito de primeira classe.

Suporte obrigatório:

- Xbox One / Series;
- DualSense / PS5;
- analógico;
- D-pad;
- deadzone;
- remapeamento;
- vibração configurável;
- desconexão/reconexão durante gameplay;
- troca automática de prompts.

Os prompts devem alternar entre:

- teclado;
- Xbox;
- PlayStation.

## Android

- controles virtuais;
- safe area;
- múltiplos aspect ratios;
- pause ao minimizar;
- retorno seguro do background.

---

# 26. Arquitetura de input

Gameplay nunca deve depender diretamente de tecla ou botão físico.

Exemplo:

```ts
enum InputAction {
  MoveLeft,
  MoveRight,
  MoveUp,
  MoveDown,
  Jump,
  Ability,
  Interact,
  Pause,
}
```

Adaptadores:

- KeyboardInputAdapter
- XboxGamepadAdapter
- DualSenseGamepadAdapter
- TouchInputAdapter

---

# 27. Save e backend futuro

No início:

- save local;
- progresso;
- tempos;
- medalhas;
- Emblemas;
- opções;
- conclusão por personagem.

Save deve ser versionado.

Backend não será construído no protótipo, mas a arquitetura deve permitir no futuro:

```text
GAME CLIENT
Cocos + TypeScript
       |
       | HTTPS
       v
BACKEND API
       |
       +-- Auth
       +-- Perfil
       +-- Cloud Save
       +-- Histórico
       +-- Ranking
       +-- Estatísticas
       +-- Conquistas
       +-- Progresso
       v
DATABASE
```

Princípio:

**offline first para campanha single-player**.

Sem internet:

- jogo continua;
- save local continua.

Ao reconectar:

- sincroniza quando possível.

Login futuro:

- e-mail;
- senha;
- recuperação;
- sessão persistente;
- possível Google/Steam depois.

Não bloquear primeiro acesso com login.

Fluxo ideal:

- Jogar sem conta;
- Criar conta para sincronizar progresso.

Cross-save futuro entre PC e Android.

---

# 28. Plataformas

## Principal — Windows

Build nativo instalável.

Referência de qualidade e performance.

## Segunda — Android

Planejado desde o primeiro dia.

## Terceira — Web

Uso secundário:

- QA;
- teste;
- demo;
- showcase;
- possível itch.io.

Não usar navegador como única validação do jogo.

---

# 29. Referências de direção

## Grapple Dog

Estudar:

- cores fortes;
- leitura de plataformas;
- personagem pequeno e expressivo;
- movimento central;
- segredos;
- bosses pontuais;
- desafios de tempo;
- momentum.

Não copiar:

- grappling hook como mecânica central;
- protagonista;
- layouts;
- identidade visual.

Referências:

- https://store.steampowered.com/app/1345860/Grapple_Dog/
- https://superraregames.com/pages/grapple-dog

## Hirocato - The Delivery Hero

Estudar:

- parkour;
- velocidade;
- pixel art moderna;
- movimento do gato;
- replay;
- leitura de chão/ar;
- cronômetro;
- personalidade no movimento.

Não copiar:

- delivery como premissa;
- rewind;
- mapas;
- protagonista.

Referências:

- https://www.astero.games/presskit/
- https://store.steampowered.com/app/2445060/

## Rayman Legends

Estudar:

- inimigos integrados ao ritmo;
- bosses baseados em movimento e contra-ataque;
- segredos;
- leitura visual;
- variação de ritmo.

Referência:

- https://www.ubisoft.com/pt-br/games/rayman-legends

Regra:

referência serve para estudar direção e experiência, nunca copiar arte, sprites, personagens, mapas ou mecânicas exatamente.

---

# 30. Roadmap oficial

## Fase 0 — Pré-produção

- Bíblia do jogo;
- direção visual;
- conceito de Biscoito;
- conceito de Mingau;
- HUD inicial.

## Fase 1 — Movement Lab

Criar sala de teste com:

- chão;
- paredes;
- rampas;
- cabos;
- buracos;
- plataformas móveis.

Implementar:

- física compartilhada;
- Biscoito;
- Mingau;
- teclado;
- Xbox;
- DualSense;
- câmera;
- 60 FPS.

Critério:

**mover-se numa sala vazia precisa ser divertido.**

## Fase 2 — Vertical Slice 1-1

Criar Trilhas da Festa com 3–5 min no primeiro protótipo.

Precisa ter:

- começo/meio/fim;
- checkpoint;
- inimigo;
- Fragmentos;
- 3 Emblemas;
- rota Biscoito;
- rota Mingau;
- tela de resultado;
- comparação de tempos;
- música;
- SFX;
- arte próxima da direção final.

## Fase 3 — Validação

Testar:

- diferença dos personagens é percebida sem tutorial longo?
- existe vontade de rejogar?
- controles Xbox/PS5 são naturais?
- 60 FPS?
- HUD legível?

## Fase 4 — Mundo 1

Produzir 1-1 até 1-5.

## Fase 5 — Mundos 2–5

Produção sequencial.

Cada mundo passa por:

- graybox;
- teste Biscoito;
- teste Mingau;
- arte;
- áudio;
- QA;
- performance.

## Fase 6 — Windows

- instalador;
- fullscreen;
- borderless;
- controles;
- remapeamento;
- vibração;
- save;
- acessibilidade;
- otimização.

## Fase 7 — Android

- touch;
- safe areas;
- otimização;
- background/resume;
- APK/AAB.

## Fase 8 — Backend/Conta

- autenticação;
- cloud save;
- histórico;
- ranking;
- estatísticas;
- conquistas;
- cross-save.

---

# 31. Regras que não podem ser quebradas

1. Movimento é o produto principal.
2. Biscoito e Mingau nunca são apenas skins.
3. Mesma campanha para os dois.
4. Sem troca instantânea durante a fase.
5. Replay é parte do design.
6. Não transformar o projeto em RPG.
7. Combate nunca domina plataforma.
8. Boss não é saco de HP.
9. Rota principal funciona com ambos.
10. Arte deve ser legível em movimento.
11. Windows nativo é a referência principal.
12. Xbox e DualSense/PS5 são requisitos de primeira classe.
13. Android deve ser considerado desde a arquitetura inicial.
14. Backend futuro nunca pode tornar a campanha single-player dependente de internet.
15. Toda nova mecânica precisa melhorar movimento, leitura, exploração ou replay.

## Prioridade permanente

**MOVIMENTO > LEVEL DESIGN > LEITURA VISUAL > ÁUDIO > CONTEÚDO > SISTEMAS ONLINE.**
