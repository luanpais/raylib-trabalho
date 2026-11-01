# 3.1 O que é o software?

Fontes: README, CONTRIBUTING.md, Wiki e página de releases do repositório (consultadas em 01/nov/2026).

| Item | Descrição | Evidência |
|---|---|---|
| Problema que resolve | Oferece uma forma simples de programar jogos, ferramentas e aplicações gráficas sem engine pesada: "sem interface, sem botões de debug... só código". | README: "simple and easy-to-use library to enjoy videogames programming" |
| Público-alvo | Estudantes e educadores, prototipadores, desenvolvedores de ferramentas, sistemas embarcados. | README: "especially well suited for prototyping, tooling, graphical applications, embedded systems and education" |
| Principais usuários | (1) Quem aprende programação gráfica; (2) desenvolvedores independentes de jogos/ferramentas; (3) portadores para plataformas incomuns (ESP32, consoles retrô, AmigaOS); (4) mantenedor e contribuidores. | README; release 5.5 (consoles retrô); release 6.0 (porte ESP32 da Espressif); issue #5978 (autor porta para AmigaOS 3.2) |
| Funcionalidades | Janela/entrada multiplataforma; 2D (formas, texturas, texto); 3D (modelos, animação esquelética IQM/M3D/glTF); shaders; áudio (WAV, QOA, OGG, MP3, FLAC, XM, MOD); `raymath`; camada OpenGL própria `rlgl`; renderizador por software `rlsw`; 140+ exemplos; bindings para 70+ linguagens. | README (seção *features*) |
| Tecnologias | C99 (PascalCase/camelCase); OpenGL 1.1/2.1/3.3/4.3/ES2/ES3; backends de plataforma GLFW/SDL/RGFW/Win32/DRM/Android/Emscripten; CMake/Makefile/build.zig; GitHub Actions. | README; árvore de arquivos (`CMakeLists.txt`, `build.zig`, `.github`); releases 5.0/5.5/6.0 |
| Licença | zlib/libpng não modificada (OSI; permite linkagem estática com código fechado). Libs em `src/external` têm licenças próprias. | README (seção *license*); arquivo `LICENSE` |
| Versão analisada | **6.2** — 15/out/2026, commit `0256645`; "+10280 commits, 619 funções na API, +225 exemplos, +950 contribuidores". | Página de releases |

**Limitações declaradas pelo próprio projeto** (úteis para a análise): janela única/contexto único; redimensionar/mover a janela pausa o loop de render em algumas plataformas; sem RTL, ligaduras e emojis no texto. (README, seção *limitations*)

## Personas e Jobs to Be Done

> **Atenção metodológica:** são *proto-personas* derivadas de evidências públicas (README, CONTRIBUTING, releases, issues), **não de entrevistas**.
> A dupla deve declarar isso na apresentação e, se possível, validar com um usuário real (Discord/Reddit do projeto).

### Persona 1 — Marina, estudante de Computação (aprendiz)
- **Contexto:** cursa computação gráfica/jogos, conhece C básico, quer ver resultado na tela rápido.
- **Evidência:** CONTRIBUTING ("educators and institutions can use this tool to TEACH videogames programming completely for free"); README ("Ready to learn? Jump to code examples!").
- **JTBD:** *Quando* começo a estudar programação gráfica, *quero* abrir uma janela e desenhar com poucas linhas, sem instalar dependências, *para* focar nos conceitos e não na configuração do ambiente.

### Persona 2 — Victor, desenvolvedor embarcado/portador
- **Contexto:** leva a biblioteca para hardware sem GPU ou com pouca memória (microcontroladores, consoles retrô, AmigaOS).
- **Evidência:** release 6.0 (`rlsw` útil no porte para ESP32, sem GPU); release 5.5 (Dreamcast, PSP, PSVita); issue #5978 (porte para AmigaOS 3.2; escolha de D8 "para economizar memória").
- **JTBD:** *Quando* preciso rodar gráficos em um dispositivo com CPU e RAM limitadas, *quero* ajustar em tempo de compilação o consumo de memória do renderizador, *para* manter a mesma API do raylib sem reescrever meu código.

### Persona 3 — Lúcia, desenvolvedora independente de jogos 2D
- **Contexto:** prototipa jogos/ferramentas e quer controle total do código.
- **Evidência:** README ("prototyping, tooling"); release 6.2 (API de desenho espelhada entre tela e `Image`); release 5.5 (*project creator* com CI/CD pré-configurado).
- **JTBD:** *Quando* estou prototipando uma ideia de jogo, *quero* uma API pequena e consistente (tela e imagem), *para* iterar rápido e distribuir para várias plataformas.
