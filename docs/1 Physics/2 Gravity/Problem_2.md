# Problem 2
##  Problem 2 – Escape Velocities and Cosmic Velocities

###  Explanation

### 1. Definitions:
- **First Cosmic Velocity ($v_1$)** – orbital velocity: the speed needed to maintain a circular orbit near the surface.
  $$v_1 = \sqrt{\frac{G M}{R}}$$

- **Second Cosmic Velocity ($v_2$)** – escape velocity: the speed required to break free from a celestial body's gravitational field without further propulsion.
  $$v_2 = \sqrt{\frac{2 G M}{R}}$$

- **Third Cosmic Velocity ($v_3$)** – interstellar escape velocity: the minimum speed needed to escape the gravity of an entire star system (e.g., Solar System).

  For approximation:
  $$v_3 \approx \sqrt{v_{Earth-orbit}^2 + v_{escape-Sun}^2}$$

---

### 2. Python Code to Compute and Plot the Velocities

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
G = 6.67430e-11  # gravitational constant in m^3 kg^-1 s^-2

# Planetary data: name, radius (m), mass (kg)
bodies = {
    'Earth':    {'R': 6.371e6,  'M': 5.972e24},
    'Mars':     {'R': 3.390e6,  'M': 6.417e23},
    'Jupiter':  {'R': 6.9911e7, 'M': 1.898e27}
}

# Prepare results
names = []
v1 = []  # Orbital velocity
v2 = []  # Escape velocity

for body, data in bodies.items():
    R = data['R']
    M = data['M']
    names.append(body)
    v1.append(np.sqrt(G * M / R))
    v2.append(np.sqrt(2 * G * M / R))

# Plotting
x = np.arange(len(names))
width = 0.35

plt.figure(figsize=(10, 6))
plt.bar(x - width/2, v1, width, label='First Cosmic Velocity $v_1$', color='skyblue')
plt.bar(x + width/2, v2, width, label='Second Cosmic Velocity $v_2$', color='orange')

plt.xticks(x, names)
plt.ylabel('Velocity (m/s)')
plt.title('Cosmic Velocities for Celestial Bodies')
plt.legend()
plt.grid(axis='y')
plt.tight_layout()
plt.show()
```
![alt text](image-1.png)

---

### 3. Applications in Space Exploration

- **$v_1$** – Used to place satellites into low Earth orbit (LEO), GPS, and communication satellites.
- **$v_2$** – Required for missions to the Moon, Mars, and beyond.
- **$v_3$** – Required to leave the Solar System; achieved by spacecraft like Voyager 1 and 2.

---

###  Summary
- Derived and computed $v_1$, $v_2$, and discussed $v_3$
- Applied to Earth, Mars, and Jupiter
- Visualized their significance for space missions and satellite deployment
