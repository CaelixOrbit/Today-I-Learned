# 常见单边序列 $z$ 变换及其收敛域

|            序列             |                             $z$ 变换                             |               收敛域                |
| :-------------------------: | :--------------------------------------------------------------: | :---------------------------------: |
|         $\delta[n]$         |                               $1$                                |        $\lvert z \rvert > 0$        |
|           $u[n]$            |                     $\dfrac{1}{1 - z^{-1}}$                      |        $\lvert z \rvert > 1$        |
|         $-u[-n-1]$          |                     $\dfrac{1}{1 - z^{-1}}$                      |        $\lvert z \rvert < 1$        |
|          $n u[n]$           |                 $\dfrac{z^{-1}}{(1 - z^{-1})^2}$                 |        $\lvert z \rvert > 1$        |
|        $-n u[-n-1]$         |                 $\dfrac{z^{-1}}{(1 - z^{-1})^2}$                 |        $\lvert z \rvert < 1$        |
|         $a^n u[n]$          |                    $\dfrac{1}{1 - a z^{-1}}$                     | $\lvert z \rvert > \lvert a \rvert$ |
|       $-a^n u[-n-1]$        |                    $\dfrac{1}{1 - a z^{-1}}$                     | $\lvert z \rvert < \lvert a \rvert$ |
|        $n a^n u[n]$         |               $\dfrac{a z^{-1}}{(1 - a z^{-1})^2}$               | $\lvert z \rvert > \lvert a \rvert$ |
|      $-n a^n u[-n-1]$       |               $\dfrac{a z^{-1}}{(1 - a z^{-1})^2}$               | $\lvert z \rvert < \lvert a \rvert$ |
|   $\cos(\Omega_0 n) u[n]$   |    $\dfrac{z(z - \cos \Omega_0)}{z^2 - 2z \cos \Omega_0 + 1}$    |        $\lvert z \rvert > 1$        |
|   $\sin(\Omega_0 n) u[n]$   |      $\dfrac{z \sin \Omega_0}{z^2 - 2z \cos \Omega_0 + 1}$       |        $\lvert z \rvert > 1$        |
| $a^n \cos(\Omega_0 n) u[n]$ | $\dfrac{z(z - a \cos \Omega_0)}{z^2 - 2z a \cos \Omega_0 + a^2}$ | $\lvert z \rvert > \lvert a \rvert$ |
| $a^n \sin(\Omega_0 n) u[n]$ |   $\dfrac{z a \sin \Omega_0}{z^2 - 2z a \cos \Omega_0 + a^2}$    | $\lvert z \rvert > \lvert a \rvert$ |
