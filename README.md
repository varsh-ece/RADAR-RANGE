# RADAR-RANGE

# AIM

To study the variation of radar range with respect to transmitted power, antenna gain, and minimum detectable power using the radar range equation.

# APPARATUS / SOFTWARE REQUIRED

PC INSTALLED WITH SCILAB

Computer system with plotting capability

# THEORY

The radar range equation expresses the relationship between transmitted power, antenna gains, wavelength, radar cross section, and receiver sensitivity to determine the maximum distance at which a radar can detect a target.

The parameters involved are:

Pt – Transmitted power (W)

Gt – Transmitting antenna gain

Gr – Receiving antenna gain

L – Wavelength (m)

sigma – Radar cross section of the target (m²)

Pmin – Minimum detectable signal power (W)

R – Maximum radar range (m)

From the radar range equation,

The range increases with transmitted power.

The range increases with antenna gain.

The range decreases as minimum detectable power increases.

Thus, the radar’s performance mainly depends on transmitted power, antenna efficiency, and receiver sensitivity.

# PROCEDURE

Initialize constants:
Speed of light c = 3 × 10⁸ m/s
Transmitting gain Gt = 50
Receiving gain Gr = 50
Wavelength L = 0.03 m
Radar cross section sigma = 10
Minimum detectable power Pmin = 1 × 10⁻⁹ W

Case 1 – Variation with transmitted power:
Vary Pt from 0 to 5 W in steps of 0.05 and calculate the radar range R.
Plot R versus Pt.

Case 2 – Variation with antenna gain:
Fix Pt = 1 W and vary gain G from 0 to 5 in steps of 0.05.
Plot R versus G.

Case 3 – Variation with receiver sensitivity:
Fix Pt = 1 W and vary Pmin from 1 × 10⁻¹² to 1 × 10⁻⁸ W.
Plot R versus Pmin.

Display all three plots using the subplot command for comparison.

# PROGRAM:
```
c=3e8;
Gt=50;
Gr=50;
L=0.03;
sigma=10;
Pmin=1e-9;

Pt=0:0.05:5; 
R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,1);
plot(Pt,R);

G=0:0.05:5;

Pt=1;
R = (((Pt .* G .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,2);
plot(G,R);

Gt=50;
Gr=50;
Pmin=1e-12:1e-12:1e-8;
R = (((Pt .* Gt .* Gr .* L.^2 .* sigma) ./ (((4 * %pi)^3) .* Pmin)) ).^(1/4);
subplot(3,1,3);
plot(Pmin,R);
```
# OUTPUT WAVEFORM:
<img width="744" height="647" alt="image" src="https://github.com/user-attachments/assets/013500e8-dcf5-46b5-a667-7a5819768e2c" />

# THEORETICAL CALCULATION:
![WhatsApp Image 2025-11-03 at 13 59 14_9fdc68c4](https://github.com/user-attachments/assets/e705addf-787b-4ed4-a347-07330e7839ce)



# RESULT

As transmitted power increases, radar range also increases.

As antenna gain increases, radar range increases.

As minimum detectable power increases (receiver becomes less sensitive), radar range decreases.
