### Theory 

<p>When AC is applied to the parallel RC circuit shown below, the capacitor never reaches a final charge and therefore it will always carry some current.</p>

<p>To make matters more interesting, we know that the voltage in a parallel circuit must be the same throughout the circuit. However, the current through <strong>R</strong> is not the same as the current through <strong>C</strong>. Thus, <em>I<sub>R</sub></em> is in phase with <em>V</em>, but <em>I<sub>C</sub></em> leads <em>V</em> by 90°.</p>

<p>Because the voltage is the same throughout the circuit, we must use voltage as the reference and determine the total circuit current in terms of that voltage. To do this, we turn to Ohm's Law. We already know that:</p>

<p><em>I<sub>R</sub> = V / R</em></p>

<p>But that +90° phase shift in <strong>C</strong> requires the use of complex numbers here, so:</p>

<p><em>I<sub>C</sub> = j(V / X<sub>C</sub>)</em></p>

<p>The total current then is:</p>


$$I=\frac{V}{Z}=\frac{V}{R}+j\frac{V}{XC}$$

<p>There are two things to note about this equation. First, keep in mind that <em>j(V / X<sub>C</sub>) = V / (−jX<sub>C</sub>)</em>. Another way to look at this is to note that capacitive reactance is ultimately defined as <em>X<sub>C</sub> = 1 / (ωC)</em>. Including the "j" factor, we have <em>1 / (jωC)</em>. This again gives us <em>−jX<sub>C</sub></em> for capacitive reactance.</p>

<p>The second point is, since <em>V</em> is the same in all terms of this equation, we can divide each term by <em>V</em> and thus remove it from our calculations. Therefore, the complex equation we really need to solve is:</p>

$$\frac{1}{Z}=\frac{1}{R}+\frac{1}{-jXC}$$


<p>The above equation is simply the beginning of the general equation for impedances in parallel. The only twist is that one is a reactance while the other is a resistance. Therefore, we need to deal with that pesky "<em>j</em>" in one term. Fortunately, this isn't as difficult as it might seem at first.</p>

<p>The expression for impedances in parallel is simply an update of the expression for resistors in parallel. If we first collect any multiple resistors together to form a composite <strong>R</strong>, and also determine a single composite <strong>C</strong> and a single composite <strong>L</strong>, the general expression for these elements in parallel becomes:</p>

$$Z = \frac{R \cdot j(X_L - X_C)}{R + j(X_L - X_C)}$$


In this case, we only have R and C, so the XL factors simply drop out of the equation, leaving us with:

$$Z = \frac{R \cdot (-jX_C)}{R - jX_C}$$

<p>To complete this calculation, we must remove the "<em>j</em>" term from the denominator. We can do this by applying the mathematical identity:</p>

$$(a + b)(a - b) = a^2 - b^2$$

In this case,

$$(R + jX_C)(R - jX_C) = R^2 - j^2X_C^2 = R^2 + X_C^2$$

Thus, we can multiply the parallel expression by (R+jXC)/(R+jXC) and get the following result:

$$Z = \frac{R \cdot (-jX_C)}{R - jX_C} \cdot \frac{R + jX_C}{R + jX_C}$$


$$= \frac{(-jR X_C)(R + jX_C)}{(R - jX_C)(R + jX_C)}$$

$$= \frac{-jR^2 X_C - j^2 R X_C^2}{R^2 + X_C^2}$$

$$= \frac{R X_c^2 - j R^2 X_c}{R^2 + X_c^2}$$

<p>
  This expression gives us an entirely real number in the denominator, which in turn makes the necessary computations possible and practical. Our parallel RC impedance now has a real term and a "j" term, and can be written as:
</p>

$$Z = \frac{R X_c^2}{R^2 + X_c^2} - j \frac{R^2 X_c}{R^2 + X_c^2}$$

<p>
  This expression can now be used to calculate the parallel impedance of any resistor and any capacitor, provided the signal frequency is known.
</p>

<p>
  To verify this mathematical expression, let's try a practical example. Let V = 10 volts RMS, with R = 10Ω, C = 0.01F, and frequency = 100 Hz. Then:
</p>


$$X_c = \frac{1}{2 \pi \cdot 100 \cdot 0.01} = 0.15915\, \Omega$$

$$I_R=\frac{V}{R}=\frac{10}{10}=1 \text{A}$$

$$I_c = \frac{V}{-j X_c} = \frac{10}{-j \cdot 0.15915} = j\,62.83\,\text{A}$$

$$I_T = \left( I_R^2 + I_C^2 \right)^{1/2} = \left( 1 + 3948 \right)^{1/2} = 62.84\,\text{A}$$

$$Z = \frac{V}{I_T} = \frac{10}{62.84} = 0.1591\,\Omega$$

 

The next step is to calculate Z using the equation we derived earlier, and compare that result with the result above. If we've done our math correctly, the results should match. For simplicity we will first calculate the denominator (D) value and the two numerators (N1 and N2). Then we can insert those values into the final equation.

$$D = R^2 + X_c^2 = 10^2 + 0.15915^2 = 100 + 0.0253287552 = 100.0253287552$$

$$N1 = R X_c^2 = 10 \cdot 0.15915^2 = 10 \cdot 0.0253287552 = 0.253287552$$

$$N2 = R^2 X_c = 100^2 \cdot 0.15915 = 100 \cdot 0.15915 = 15.915$$

Now we can insert these values into the full equation and solve Z:

$$Z = \frac{N1}{D} - j\,\frac{N2}{D}$$
$$= \frac{0.2533}{100.02533} - j\,\frac{15.915}{100.02533}$$
$$= 0 - j\,0.1591$$
$$Z = \left(0^2 + 0.1591^2\right)^{1/2} = \left(0.1591^2\right)^{1/2}$$
$$= 0.1591\,\Omega$$

We see that both sets of calculations produce precisely the same answer. This indicates that our method for calculating impedance without using (or knowing) the signal voltage is perfectly valid.
 
This can be verified using the simulator by creating the above mentioned parallel RC circuit and by measuring the current and voltage across the resistor and capacitor. It should be consistent with the earlier findings.

### Applications:
 

It can be used as

   1. Oscillators

   2. RC filter calculator

   3. Voltage dividing circuit

   4. Coupling and wave shaping circuits





