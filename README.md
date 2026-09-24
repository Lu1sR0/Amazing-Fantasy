<div align="center">

# Amazing Fantasy

Livro 3D interativo no navegador, com as páginas da HQ que marcou a estreia do Homem-Aranha.

[![Ver site](https://img.shields.io/badge/VER_SITE-0D0D0D?style=for-the-badge&logo=vercel&logoColor=FF003C)](https://amazingfantasy.vercel.app)

![React](https://img.shields.io/badge/React-0D0D0D?style=for-the-badge&logo=react&logoColor=FF003C)
![Vite](https://img.shields.io/badge/Vite-0D0D0D?style=for-the-badge&logo=vite&logoColor=FF003C)
![Three.js](https://img.shields.io/badge/Three.js-0D0D0D?style=for-the-badge&logo=threedotjs&logoColor=FF003C)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-0D0D0D?style=for-the-badge&logo=tailwindcss&logoColor=FF003C)

</div>

## Sobre

Experiência 3D feita com React Three Fiber que simula uma revista em quadrinhos física. A capa e as páginas de *Amazing Fantasy* #15 (1962) viram texturas de um livro que flutua na tela e pode ser folheado com o mouse ou pelos botões de navegação.

Cada página é uma malha com esqueleto (`SkinnedMesh` com 30 ossos), o que permite curvar o papel durante a virada em vez de girar um plano rígido. Ao fundo, um letreiro com "Spider Man · Amazing Fantasy" rola continuamente sobre um gradiente vermelho.

## Funcionalidades

- **Páginas que se curvam**: a virada combina curvatura interna, externa e dobra, com interpolação suave (`maath/easing`).
- **Navegação por clique**: clique numa página para avançar ou voltar. Ao passar o mouse, a página recebe um leve brilho e o cursor muda.
- **Barra de navegação**: botões para Capa, Página 1 a 6 e Contra Capa. Ao saltar várias páginas, o livro folheia uma a uma até o destino.
- **Som de virada de página** a cada mudança.
- **Cena interativa**: livro flutuando (`Float`), câmera orbital (`OrbitControls`), iluminação de estúdio (`Environment`) e sombra projetada no chão.
- **Tela de carregamento** do Drei enquanto as texturas são carregadas.
- **Letreiro animado** em loop, feito com keyframes personalizados no Tailwind.

## Tecnologias

- [React 18](https://react.dev/) + [Vite 4](https://vitejs.dev/)
- [Three.js](https://threejs.org/) (0.166)
- [@react-three/fiber 8](https://github.com/pmndrs/react-three-fiber) e [@react-three/drei 9](https://github.com/pmndrs/drei)
- [Jotai](https://jotai.org/): estado da página atual, compartilhado entre a interface e a cena 3D
- [maath](https://github.com/pmndrs/maath): interpolação das rotações dos ossos
- [Tailwind CSS 3](https://tailwindcss.com/)

## Estrutura

```
src/
├── App.jsx              # Canvas, Loader e interface
└── components/
    ├── Book.jsx         # Geometria, ossos e animação das páginas
    ├── Experience.jsx   # Cena: Float, OrbitControls, luz e sombra
    └── UI.jsx           # Navegação, som e letreiro animado
public/
├── textures/            # Capa e páginas da HQ
└── audios/              # Som de virada de página
```

## Como rodar localmente

Pré-requisito: [Node.js](https://nodejs.org/) instalado.

```bash
git clone https://github.com/Lu1sR0/Amazing-Fantasy.git
cd Amazing-Fantasy
yarn
yarn dev
```

Para gerar a versão de produção: `yarn build` e `yarn preview`.

## Créditos

- Projeto desenvolvido acompanhando o tutorial de livro 3D animado com React Three Fiber do [Wawa Sensei](https://www.youtube.com/@WawaSensei).
- Homem-Aranha e *Amazing Fantasy* pertencem à Marvel. Projeto de estudo, sem fins comerciais.

---

<div align="center">
Desenvolvido por <a href="https://github.com/Lu1sR0">Luis Roberto</a> · <a href="https://outframe.dev">Outframe</a>
</div>
