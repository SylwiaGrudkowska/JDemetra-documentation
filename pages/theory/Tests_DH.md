---
layout: left-menu
title: Doornik-Hansen test
tagline: technical documentation for JDemetra+ using GitHub Pages
description: Basics
---

The Doornik-Hansen test for multivariate normality (DOORNIK, J.A., and
HANSEN, H. (2008)) is based on the skewness and kurtosis of multivariate
data that is transformed to ensure independence. It is more powerful
than the Shapiro-Wilk test for most tested multivariate
distributions[^80].

The skewness and kurtosis are defined, respectively, as:
$$s = \frac{m_{3}}{\sqrt{m_{2}}^{3}}$$ and
$k = \frac{m_{4}}{m_{2}^{2}},\ $where:
$m_{i} = \frac{1}{n}\sum_{i = 1}^{n}{(x_{i}}{- \overline{x})}^{i}$
$\overline{x} = \frac{1}{n}\sum_{i = 1}^{n}x_{i}$ and $n$ is a number of
(non-missing) residuals.

The Doornik-Hansen test statistic derives from SHENTON, L.R., and
BOWMAN, K.O. (1977) and uses transformed versions of skewness and
kurtosis.

The transformation for the skewness $s$ into$\text{z}_{1}$ is as in
D\'AGOSTINO, R.B. (1970):

  $$
  \beta = \frac{3(n^{2} + 27n - 70)(n + 1)(n + 3)}{(n - 2)(n + 5)(n + 7)(n + 9)}
  $$  \[1\] <!---\[7.130\]      -->
  
  $$
  \omega^{2} = - 1 + \sqrt{2(\beta - 1)}
  $$ \[2\] <!---\[7.131\]      -->                                       
  
  $$
  \delta = \frac{1}{\sqrt{\log{(\omega}^{2})}}
  $$ \[3\] <!---\[7.132\]      -->                                 
  
  $$
  y = s\sqrt{\frac{(\omega^{2} - 1)(n + 1)(n + 3)}{12(n - 2)}}
  $$    \[4\] <!---\[7.133\]      -->                 
  
  $$
  z_{1} = \delta log(y + \sqrt{y^{2} - 1})
  $$     \[5\] <!---\[7.134\]      -->                                  

The kurtosis $k$ is transformed from a gamma distribution to $\chi^{2}$,
which is then transformed into standard normal $z_{2}$ using the
Wilson-Hilferty cubed root transformation:

  $$
  \delta = (n - 3)(n + 1)(n^{2} + 15n - 4)
  $$       \[6\] <!---\[7.135\]      -->                                              
  
  $$
  a = \frac{(n - 2)(n + 5)(n + 7)(n^{2} + 27n - 70)}{6\delta}
  $$    \[7\] <!---\[7.136\]      -->                               
  
  $$
  c = \frac{(n - 7)(n + 5)(n + 7)(n^{2} + 2n - 5)}{6\delta}
  $$ \[8\] <!---\[7.137\]      -->                                   
  
  $$
  l= \frac{(n + 5)(n + 7)({n^{3} + 37n}^{2} + 11n - 313)}{12\delta}
  $$  \[9\] <!---\[7.138\]      -->                       
  
  $$
  \alpha = a + c \times s^{2}
  $$ \[10\] <!---\[7.139\]      -->                                                                  
  
  $$
  \chi = 2l(k - 1 - s^{2})
  $$    \[11\] <!---\[7.140\]      -->                                                                 
  
  $$
  z_{2} = \sqrt{9\alpha}\left( \frac{1}{9\alpha} - 1 + \sqrt[3]{\frac{\chi}{2\alpha}} \right)
  $$   \[12\] <!---\[7.141\]      -->

Finally, the Doornik-Hansen test statistic is defined as the sum of
squared transformations of the skewness and kurtosis. Approximately, the
test statistic follows a $\chi^{2}$distribution, i.e.:


  $$
  DH = z_{1}^{2} + z_{2}^{2}\sim\chi^{2}(2)
  $$   \[13\] <!---\[7.142\]      -->
  
  
  [^80]: The description of the test derives from DOORNIK, J.A., and
    HANSEN, H. (2008).
