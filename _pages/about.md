---
permalink: /
title: "Wind Tunnel for Pollination Device Testing"

excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

We are currently constructing a wind tunnel for testing pollination devices. Epoxy numerical hand-pasting techniques are being used in the fabrication of the expansion section of the wind tunnel. The contraction section is currently under design and is expected to be completed before the Chinese New Year. This project poses a challenging task. There are uncertainties regarding the contraction section of the wind tunnel, particularly in the selection between the fifth-power curve and the Witoszynski curve. Personally, I prefer the Witoszynski curve. The origin of the Witoszynski curve is mysterious, and Witoszynski himself disappeared without a trace after leaving only this article in Springer. Nevertheless, his research findings are widely circulated. Below is a MATLAB code segment designed by me for plotting the Witoszynski curve, including its multiple derivatives. Due to the special nature of the function construction, the curve remains smooth and continuous regardless of how many times it is differentiated.
![Editing a markdown file for a talk](/images/Home1.JPG)
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

Kiwi Precision Liquid Pollination Device
======
This is a precision liquid pollination device designed for kiwi pollination. It allows precise control of the amount of kiwi pollen solution, and the motion stroke of the gas-liquid pressure lever is measured using a grating ruler. Currently, I am continuously optimizing it.

Kiwi Vortex Pollination Device
======
This is a vortex pollination device for kiwi, involving the technical field of fruit tree pollination devices. It includes a pollen feeder, a pollen mixer, and a vortex generator. The pollen feeder transports pollen to the pollen mixer, which mixes the pollen with gas to form a pollen-air mixture. The pollen mixer can also discharge the pollen-air mixture into the vortex generator, which emits vortices formed by the pollen-air mixture. The vortex generator has a vortex generation chamber, and inside the chamber, there is a first concentration monitoring device. The first concentration monitoring device monitors the concentration of pollen inside the vortex generation chamber. When the concentration reaches the set threshold, the vortex generator emits vortices outward.

ICCV2023
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the academicpages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring academicpages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful.
