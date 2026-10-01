# ODISSEIA

> **Hardware reaproveitado + Linux customizado + IA educacional = um cyberdeck aberto, modular e experimental.**

<p align="center">
  <img src="https://github.com/caesarcarl/Projeto-odisseia/blob/main/assets/screenshots/Monitor%20Hefestos%20OS%20em%20Forge%20Cibern%C3%A9tica.png" alt="Projeto Odisseia" width="900">
</p>

<p align="center">
  <b>Transformando silício descartado em autonomia tecnológica.</b><br>
  São Luís, Maranhão • Projeto educacional • Cultura Maker • Linux • IA
</p>

<p align="center">
  <a href="#-o-projeto">Projeto</a> •
  <a href="#-arquitetura">Arquitetura</a> •
  <a href="#-odisseia-mobile">Mobile</a> •
  <a href="#-atena-ia">Atena IA</a> •
  <a href="#-estado-atual">Estado</a> •
  <a href="docs/ROADMAP.md">Roadmap</a> •
  <a href="docs/TECHNICAL.md">Documentação técnica</a>
</p>

---

## 🌌 O projeto

**Odisseia** é um ecossistema experimental de computação voltado a reaproveitamento de hardware, Linux, engenharia reversa, educação tecnológica e inteligência artificial.

A pergunta que guia o projeto não é apenas **“qual computador devemos comprar?”**, mas:

> **“O que ainda pode ser utilizado, compreendido, reparado e transformado?”**

O projeto parte de equipamentos que ainda possuem capacidade computacional e os reorganiza como plataformas abertas para estudo, programação, experimentação e criação.

O protótipo mais avançado é o **Odisseia Mobile**, construído sobre um Samsung Galaxy A11 e transformado em um cyberdeck Linux com teclado físico, interface própria e uma trilha paralela de pesquisa de Linux nativo.

---

## 🧭 Visão

```text
Hardware reaproveitado
        │
        ▼
Engenharia + recuperação
        │
        ▼
Linux / Odisseia OS
        │
        ├──────────────► Atena IA
        │                 │
        ▼                 ▼
Interface própria     Aprendizado
        │             e assistência
        └──────┬──────────┘
               ▼
        CYBERDECK ODISSEIA
```

O Odisseia não tenta esconder as limitações do hardware. Elas viram decisões de engenharia: medir, entender, preservar, modificar, testar, recuperar e documentar.

## 🧱 Os quatro pilares

| Pilar | Ideia |
|---|---|
| **Hardware reaproveitado** | Reutilizar smartphones, notebooks, SBCs e componentes ainda funcionais. |
| **Design sustentável e modular** | Construir equipamentos reparáveis, modificáveis e visualmente próprios. |
| **Linux educacional** | Usar software livre e ambientes Linux adaptados ao hardware disponível. |
| **Atena IA** | Assistente educacional híbrida, orientada ao aprendizado e ao método socrático. |

---

## 📱 Odisseia Mobile

<p align="center">
  <img src="assets/screenshots/odisseia-mobile.jpg" alt="Odisseia Mobile" width="780">
</p>

O **Odisseia Mobile** transforma um **Samsung Galaxy A11 SM-A115M / a11q** em uma plataforma de computação móvel experimental.

### Hardware-base

- Qualcomm SDM450 / família MSM8953
- 8 × Cortex-A53
- hardware com capacidade ARM64
- tela, bateria, Wi-Fi, armazenamento e USB do próprio telefone
- mini teclado físico 2.4 GHz via OTG
- Raspberry Pi 3B opcional como nó auxiliar

### Ambiente operacional demonstrável

```text
Odisseia Launcher / Kiosk
          │
          ▼
      KeX / VNC
          │
          ▼
     XFCE + Linux
          │
          ▼
 Kali / NetHunter ARMHF
          │
          ▼
Android modificado + Magisk
          │
          ▼
Kernel Samsung + hardware Galaxy A11
```

No modo Cyberdeck, o Android continua sendo usado como camada de habilitação de hardware, enquanto a experiência principal é entregue pelo ambiente Odisseia/Linux.

Em paralelo existe o **Odisseia Native**, uma frente de pesquisa que já explorou boot com kernel Samsung e initramfs/userspace próprio, reduzindo progressivamente a dependência do userspace Android.

> O modo Cyberdeck e o ramo Native são frentes diferentes. O repositório evita apresentar pesquisa em andamento como funcionalidade concluída.

---

## 🔥 Hefestos OS

<p align="center">
  <img src="assets/screenshots/hefestos-os.jpg" alt="Hefestos OS" width="780">
</p>

**Hefestos OS** representa a frente de interface e identidade para equipamentos reaproveitados e nós do ecossistema Odisseia. A proposta visual combina desktop Linux, ferramentas locais e uma interface dedicada, em vez de deixar o equipamento com aparência de uma distribuição genérica.

---

## 🧠 Atena IA

<p align="center">
  <img src="assets/screenshots/atena-ia.jpg" alt="Atena IA" width="780">
</p>

**Atena** é a camada de inteligência artificial do ecossistema. Sua proposta é funcionar como assistente de conhecimento e estudo, incluindo uma abordagem socrática: ajudar o usuário a construir raciocínio, e não apenas despejar respostas prontas.

O código da Atena vive em um repositório separado:

**[caesarcarl/Atena-IA](https://github.com/caesarcarl/Atena-IA)**

O repositório da Atena é o projeto de software da IA. Este repositório do **Odisseia** funciona como vitrine, documentação de arquitetura, histórico de engenharia e ponto de integração do ecossistema.

---

## ⚙️ Engenharia por trás do Mobile

O trabalho no Galaxy A11 incluiu:

- inventário do aparelho por ADB, `/proc`, sysfs e propriedades Android;
- preservação de firmware stock, PIT e hashes;
- estudo do `boot.img`, kernel, ramdisk e Device Tree;
- identificação de Android Boot Image v2;
- análise de multi-DTB;
- root e automação via Magisk;
- Linux em chroot com XFCE;
- TigerVNC/KeX para sessão gráfica;
- launcher Android próprio, kiosk e lockscreen;
- watchdog, checkpoints e rotas de rollback;
- integração de teclado físico;
- experimentos de userspace Linux próprio;
- ferramentas em **Shell, Python, C/C++ e Java/Android**.

Leia: **[Documentação técnica](docs/TECHNICAL.md)**.

---

## 🧩 Componentes do ecossistema

| Componente | Papel | Situação |
|---|---|---|
| **Odisseia Mobile** | Cyberdeck baseado no Galaxy A11 | Protótipo funcional / evolução |
| **Odisseia Native** | Pesquisa de Linux mais próximo do hardware | Experimental |
| **Odisseia OS** | Identidade e arquitetura Linux do ecossistema | Em evolução |
| **Hefestos OS** | Interface/sistema para nós e hardware reaproveitado | Em evolução |
| **Atena IA** | Assistente educacional e de conhecimento | Repositório próprio |
| **Odisseia Node** | Expansão com Raspberry Pi | Opcional / integração |

---

## 📊 Estado atual

O objetivo deste repositório é ser tecnicamente honesto: **código existente, teste em hardware e ideia futura não são a mesma coisa**.

| Frente | Estado documentado |
|---|---|
| Inventário e recuperação do Galaxy A11 | ✅ Consolidado |
| Root / Magisk | ✅ Executado |
| Linux chroot + XFCE | ✅ Executado |
| Teclado físico | ✅ Executado |
| Launcher / kiosk | 🧪 Implementado e em validação/evolução |
| Estabilização KeX/VNC | 🧪 Mitigações implementadas |
| Controles integrados | 🧪 Código disponível / validação integrada |
| Linux Native | 🔬 Pesquisa e bring-up |
| Raspberry Pi Node | 🔬 Expansão opcional |
| Acabamento físico final | 🚧 Em desenvolvimento |

Legenda: ✅ executado • 🧪 protótipo/validação • 🔬 pesquisa • 🚧 desenvolvimento.

---

## 🗂️ Estrutura deste repositório

```text
Odisseia/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── SECURITY.md
├── CITATION.cff
├── docs/
│   ├── ARCHITECTURE.md
│   ├── TECHNICAL.md
│   ├── ROADMAP.md
│   ├── ATENA.md
│   └── MEDIA.md
├── assets/
│   ├── branding/
│   │   └── odisseia-banner.png
│   └── screenshots/
│       ├── odisseia-mobile.jpg
│       ├── hefestos-os.jpg
│       └── atena-ia.jpg
└── .github/
    └── ISSUE_TEMPLATE/
        └── documentation.md
```

Este é deliberadamente um **repositório de apresentação e documentação**. Implementações podem viver em repositórios próprios.

---

## 🧪 Filosofia de engenharia

1. **Preservar antes de modificar.**
2. **Medir antes de assumir.**
3. **Separar demonstração funcional de pesquisa experimental.**
4. **Manter uma rota de recuperação conhecida.**
5. **Documentar falhas, não apenas sucessos.**
6. **Transformar comandos repetitivos em ferramentas reproduzíveis.**
7. **Reaproveitar hardware sem fingir que suas limitações não existem.**

---

## 🗺️ Roadmap

As próximas linhas de trabalho incluem estabilização do cyberdeck, acabamento físico, consolidação das bridges de hardware, documentação reproduzível, evolução da Atena e pesquisa do ramo Linux nativo.

Veja o **[Roadmap completo](docs/ROADMAP.md)**.

---

## 📚 Documentação

- **[Arquitetura](docs/ARCHITECTURE.md)**
- **[Engenharia e stack técnica](docs/TECHNICAL.md)**
- **[Atena IA e integração](docs/ATENA.md)**
- **[Roadmap](docs/ROADMAP.md)**
- **[Guia de imagens e mídia](docs/MEDIA.md)**
- **[Como contribuir](CONTRIBUTING.md)**
- **[Segurança](SECURITY.md)**

---

## ⚠️ Aviso técnico

Odisseia envolve root, boot images, engenharia reversa, modificações de sistema e testes em hardware real. Operações de baixo nível podem causar perda de dados ou inutilização do dispositivo.

A documentação pública deve privilegiar experimentação em hardware próprio ou autorizado, backups, hashes, checkpoints e rotas de recuperação.

---

## 🌎 Origem

Projeto desenvolvido em **São Luís, Maranhão, Brasil**, com foco em cultura maker, aprendizado de tecnologia, reaproveitamento de hardware e autonomia computacional.

> **Transformar o silício descartado em futuro.**

---

## 📄 Licença

Antes de publicar código ou assets de terceiros, confirme as licenças de cada componente. O arquivo `LICENSE` deste kit está como modelo de decisão, não como autorização para relicenciar software de terceiros.
