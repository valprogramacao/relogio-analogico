# relogio analogico
Relógio Analógico

Relógio Analógico

Sobre

Este projeto é um relógio analógico simples com exibição digital, desenvolvido apenas com HTML, CSS e JavaScript. Ele mostra a hora atual utilizando três ponteiros (horas, minutos e segundos) e um visor digital abaixo do relógio.

Funcionalidades

Relógio analógico de 12 horas com ponteiros de horas, minutos e segundos
Visor digital (HH:MM:SS) atualizado a cada segundo
Marcas de hora a cada 30° (12 marcações)
Layout centralizado na página


Tecnologias utilizadas
HTML5
CSS3
JavaScript (DOM API, setInterval, Date)


Estrutura do projeto

├── index.html
├── script.js
└── style.css



Como funciona

index.html    define a estrutura do relógio (container, marcas, ponteiros e exibição digital).
style.css     estiliza o relógio, centraliza o layout e define tamanhos, cores e o comportamento de rotação         via           transform-origin: left para os ponteiros.
script.js obtém a hora atual com new Date() e:
Atualiza o visor digital com HH:MM:SS (função fixZero adiciona zero à esquerda quando necessário)
Rotaciona os ponteiros usando graus calculados:
Segundos: sDeg = (360 / 60) * second - 90
Minutos: mDeg = (360 / 60) * minute - 90
Horas: hDeg = (360 / 12) * hour - 90
O deslocamento -90 posiciona os ponteiros alinhados ao topo do relógio (considerando a origem de transformação à esquerda do elemento).
A atualização ocorre a cada 1000 ms via setInterval(updateClock, 1000).


Personalização

Tamanhos e cores dos ponteiros podem ser ajustados em style.css (.p_s, .p_m, .p_h).
O tamanho do relógio pode ser alterado em .relogio (width/height).
Você pode adicionar mais marcações (por exemplo, a cada 5 minutos) duplicando elementos .risco no index.html e ajustando os ângulos.

Limitações e melhorias sugeridas
Ponteiro de horas não considera a fração dos minutos. Uma versão mais precisa pode usar:
hDeg = (360 / 12) * hour + (360 / 12) * (minute / 60) - 90
Tornar o relógio responsivo (usar unidades relativas ao invés de valores fixos).
Acessibilidade: adicionar descrições ARIA para o relógio digital e analógico.
Adicionar animação suave com requestAnimationFrame para o ponteiro de segundos.
Adicionar tema claro/escuro.