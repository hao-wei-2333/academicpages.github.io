---
permalink: /
title: "Recent Research"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
We are currently constructing a wind tunnel for testing pollination devices. Epoxy numerical hand-pasting techniques are being used in the fabrication of the expansion section of the wind tunnel. The contraction section is currently under design and is expected to be completed before the Chinese New Year. This project poses a challenging task. There are uncertainties regarding the contraction section of the wind tunnel, particularly in the selection between the fifth-power curve and the Witoszynski curve. Personally, I prefer the Witoszynski curve. The origin of the Witoszynski curve is mysterious, and Witoszynski himself disappeared without a trace after leaving only this article in Springer. Nevertheless, his research findings are widely circulated. Below is a MATLAB code segment designed by me for plotting the Witoszynski curve, including its multiple derivatives. Due to the special nature of the function construction, the curve remains smooth and continuous regardless of how many times it is differentiated.~
![Editing a markdown file for a talk](/images/Home1.JPG)
```matlab
% Import symbolic computation toolbox
syms x;

% Set constants
R1 = 190;  % Resistance 1
R2 = 95;   % Resistance 2
L = 2/3*R1;
a = sqrt(3)*L;

% Define the symbolic expression for R(x)
R_sym = R2 / sqrt(1 - (1 - (R2/R1)^2) * ((1 - (3*x^2/a^2))^2) / ((1 + (x^2/a^2))^3));

% Calculate the nth derivative of R
R_prime_3 = diff(R_sym, x, 5);

% Convert symbolic expressions to numerical functions
R = matlabFunction(R_sym);
R_prime_3_num = matlabFunction(R_prime_3);

% Define the range of x values
x_values = linspace(-L, L, 300);

% Calculate the values of R and its nth derivative
R_values = R(x_values);
R_prime_3_values = R_prime_3_num(x_values);

% Plot the original function
subplot(2, 1, 1);
plot(x_values, R_values);
title('R(x)');
xlabel('x');
ylabel('R');
grid on;

% Plot the derivative function
subplot(2, 1, 2);
plot(x_values, R_prime_3_values);
title('Third Derivative of R(x)');
xlabel('x');
ylabel('d^3R/dx^3');
grid on;
```

<img src='/images/Home2.png'>

Kiwi Precision Liquid Pollination Device
======
This is a precision liquid pollination device designed for kiwi pollination. It allows precise control of the amount of kiwi pollen solution, and the motion stroke of the gas-liquid pressure lever is measured using a grating ruler. Currently, I am continuously optimizing it.
<img src='/images/Home3.png'>

Kiwi Vortex Pollination Device
======
This is a vortex pollination device for kiwi, involving the technical field of fruit tree pollination devices. It includes a pollen feeder, a pollen mixer, and a vortex generator. The pollen feeder transports pollen to the pollen mixer, which mixes the pollen with gas to form a pollen-air mixture. The pollen mixer can also discharge the pollen-air mixture into the vortex generator, which emits vortices formed by the pollen-air mixture. The vortex generator has a vortex generation chamber, and inside the chamber, there is a first concentration monitoring device. The first concentration monitoring device monitors the concentration of pollen inside the vortex generation chamber. When the concentration reaches the set threshold, the vortex generator emits vortices outward.
<img src='/images/Home4.jpg'>

ICCV2023
======
This was an unforgettable experience. My girlfriend's paper, "LoTE-Animal: A Long Time-span Dataset for Endangered Animal Behavior Understanding," got accepted at ICCV2023. We went to Paris, France together. Although I may not fully understand everyone's research field, I got to appreciate different cultures and traditions. Here's a friendly link: 
```matlab
https://lote-animal.github.io/ 
```
If you are researching wildlife conservation, using LoTE-Animal would be an excellent choice.

<img src='/images/Home5.JPG'>
