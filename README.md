# LFSLazy + Gadgets — para o LFS 0.8C36

Este é o **LFSLazy** (patch 0.7G da comunidade) funcionando no **LFS 0.8C36**, com alguns **gadgets extras trazidos do DetectnMonitor2** (medidas de pneu, voltas, tempos de pit, etc.), mantendo o mesmo desenho do D&M.

São só dois arquivos: o `LFSLazy.exe` e o `powrprof.dll` — mantenha os dois na **mesma pasta**.

## ⬇️ Download

Baixe o zip na aba **[Releases](../../releases/latest)**. Dentro vêm o `LFSLazy.exe`, o `powrprof.dll` e o `LEIA-ME.txt`.

## É seguro?

- O `LFSLazy.exe` deste pacote é **exatamente o LFSLazy original da comunidade** (o mesmo 0.7G), sem nenhuma alteração — dá pra conferir pelo SHA-256 abaixo.
- Tudo o que é novo está no `powrprof.dll` (o "patch"): ele roda dentro do LFSLazy, **apenas lê** a memória do LFS (nunca escreve nela) e conversa com o LFS na sua própria máquina pelo InSim, como qualquer programa InSim. Não injeta nada no LFS e não manda seus dados para lugar nenhum.
- Se você apagar o `powrprof.dll`, o LFSLazy volta a ser o normal, sem os gadgets novos.
- Escaneado com o Windows Defender (proteção em tempo real ligada): **nenhuma ameaça**. Se algum antivírus reclamar, costuma ser falso positivo, comum em patches e overlays de jogo (eles mexem na memória do jogo).

### SHA-256

```
LFSLazy.exe    073b2f3464a3b169985663b690d9c32470310f39f5621059370772de9be8e246
powrprof.dll   997dfa5f4dc871f9f9c5ec4466670389bde98e9295138304e098219b6905b0f9
```

## Como usar

1. Extraia o zip numa pasta.
2. Deixe `LFSLazy.exe` e `powrprof.dll` juntos, na mesma pasta.
3. Abra o LFS. No chat do LFS, digite uma vez: `/insim 29999`
4. Abra o `LFSLazy.exe`. Na primeira vez, deixe a porta em `29999` e clique em **Continue**.
5. Entre num carro e pilote — os gadgets aparecem (somem no menu, assistindo ou no SHIFT+U).

No LFS, `Shift+I` e `Shift+B` escondem/mostram os botões de qualquer programa InSim.

## Os gadgets

| Gadget | O que mostra |
|---|---|
| **Tyre Thickness** | Banda que sobra em cada faixa do pneu, em % (100 = novo). Em cima os dianteiros, embaixo os traseiros, 3 faixas por pneu. Verde = ok, amarelo = abaixo de ~15%, vermelho = abaixo de ~4%. |
| **Ahead / Behind** | Em corrida: distância em tempo para o carro da frente / de trás na classificação, medida no mesmo ponto da pista. Em treino/classificação: diferença de melhor volta. |
| **Time-Temp** | Hora do jogo e temperatura do ar. |
| **StartStopStats** | 0–100 km/h saindo parado; e o tempo no pit lane (ao vivo), com o tempo parado no box entre parênteses. |
| **AvgLap-Stint / Clean / Total** | Média das voltas do stint / só as limpas (até 103% da média) / de toda a sessão. |
| **AvgLap** | Botão do D&M que alterna stint / clean / total a cada 5 s. |
| **Vs previous lap** | Cada parcial e cada volta comparada com a anterior: `[S1] -0.52`, `[L] +0.31`. |

As médias e o "Vs previous lap" zeram quando a corrida reinicia.

## Editar os gadgets

Menu do LFSLazy → **Gadgets** → modo de edição ("Gadgets - Edit Mode"):

- arrastar com o botão esquerdo = mover
- botão direito = liga/desliga (os desligados ficam cinza)
- a **lista de posições** do LFSLazy também liga/desliga aqui

O LFSLazy salva tudo no arquivo de configuração dele (pasta `LFSLazy\`), junto com os gadgets normais.

> Dica: não deixe o DetectnMonitor mostrando os mesmos gadgets ao mesmo tempo, senão eles ficam um por cima do outro.

## Opcional (avançado)

Os gadgets funcionam sozinhos, com valores padrão. Para mudar algo, crie um arquivo `lazypatch.ini` na mesma pasta:

```ini
[Gadgets]
Enabled=1       ; 0 desliga todos os gadgets novos
TempUnit=C      ; C ou F (Time-Temp)
AvgLapCycle=5   ; segundos entre stint/clean/total no AvgLap
MciInterval=50  ; atualizacao das posicoes (ms)
InSimPort=0     ; 0 = mesma porta do LFSLazy
```

## Créditos

- **LFSLazy** — ferramenta original da comunidade do Live for Speed.
- **Gadgets** — originais do **DetectnMonitor2** (comunidade do Live for Speed).
- Adaptação para o LFS 0.8C36 e integração dos gadgets no LFSLazy — patch **não-oficial** feito pela comunidade.

Patch não-oficial. *Live for Speed*, *LFSLazy* e *DetectnMonitor* pertencem aos seus respectivos autores.
