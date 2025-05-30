Sure! Here's a complete markdown document with embedded Python code snippets and explanations that follow the structure you requested. You can save it as a `.md` file or use it as a notebook with minor adjustments.

````markdown
# Mechanics

## Problem 1  
### Investigating the Range as a Function of the Angle of Projection

---

## Motivation

Projectile motion, while seemingly simple, offers a rich playground for exploring fundamental principles of physics. The problem is straightforward: analyze how the range of a projectile depends on its angle of projection. Yet, beneath this simplicity lies a complex and versatile framework. The equations governing projectile motion involve both linear and quadratic relationships, making them accessible yet deeply insightful.

What makes this topic particularly compelling is the number of free parameters involved in these equations, such as initial velocity, gravitational acceleration, and launch height. These parameters give rise to a diverse set of solutions that can describe a wide array of real-world phenomena, from the arc of a soccer ball to the trajectory of a rocket.

---

## 1. Theoretical Foundation

### Derivation of Governing Equations

Consider a projectile launched from the origin with initial velocity \( v_0 \) at an angle \( \theta \) from the horizontal.

- Horizontal motion (x-axis):
  
\[
x(t) = v_0 \cos\theta \cdot t
\]

- Vertical motion (y-axis):

\[
y(t) = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2
\]

where \( g \) is the gravitational acceleration (positive scalar).

The projectile lands when \( y(t) = 0 \) (ignoring launch height for now), so:

\[
0 = v_0 \sin\theta \cdot t - \frac{1}{2} g t^2 \implies t = 0 \text{ or } t = \frac{2 v_0 \sin\theta}{g}
\]

The time of flight \( T \) is the positive root:

\[
T = \frac{2 v_0 \sin\theta}{g}
\]

The range \( R \) (horizontal distance traveled) is:

\[
R = x(T) = v_0 \cos\theta \cdot T = \frac{v_0^2}{g} \sin 2\theta
\]

---

### Family of Solutions

By varying parameters \( v_0 \), \( g \), and \( \theta \), we get a family of parabolic trajectories:

- Changing \( v_0 \) scales the range quadratically.
- Changing \( g \) inversely affects the range.
- \( \theta \) controls the shape and maximum range (maximum at \( 45^\circ \)).

---

## 2. Analysis of the Range

The range as a function of the projection angle is:

\[
R(\theta) = \frac{v_0^2}{g} \sin(2\theta)
\]

- Maximum range at \( \theta = 45^\circ \) (or \( \pi/4 \) radians).
- Range is zero at \( \theta = 0^\circ \) and \( 90^\circ \).
- The function is symmetric around \( 45^\circ \).

---

## 3. Practical Applications

- Real projectiles may start at different heights, affecting the flight time.
- Air resistance (drag) reduces range and changes the shape of the trajectory.
- Uneven terrain requires adjusting the final landing height.
- External forces like wind can alter horizontal motion.

---

## 4. Implementation

```python
import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # m/s^2, gravitational acceleration

def projectile_range(v0, theta, g=g):
    """
    Calculate the horizontal range for a given initial velocity and angle.

    Parameters:
    v0 : float
        Initial velocity (m/s)
    theta : float
        Launch angle (radians)
    g : float
        Gravitational acceleration (m/s^2)

    Returns:
    float
        Horizontal range (meters)
    """
    return (v0**2 / g) * np.sin(2 * theta)

# Parameters
v0_values = [10, 20, 30]  # initial velocities in m/s
angles = np.linspace(0, np.pi/2, 180)  # from 0 to 90 degrees in radians

plt.figure(figsize=(10, 6))

for v0 in v0_values:
    ranges = projectile_range(v0, angles)
    plt.plot(np.degrees(angles), ranges, label=f'$v_0 = {v0} \\, m/s$')

plt.title('Projectile Range vs Angle of Projection')
plt.xlabel('Angle of Projection (degrees)')
plt.ylabel('Range (meters)')
plt.legend()
plt.grid(True)
plt.show()
````

---

## 5. Discussion on Model Limitations and Extensions

* The idealized model assumes no air resistance and flat terrain.
* Air resistance would require solving more complex differential equations, usually numerically.
* Launch height different from zero modifies the time of flight; formula must be adjusted accordingly.
* Incorporating wind or spin effects would require additional forces in the equations.
* The model does not account for Earth's curvature or rotation for very long-range projectiles.

---

## Summary

This study derived the fundamental equations for projectile motion and analyzed the dependence of range on the angle of projection. A computational model was developed to visualize how initial velocity and gravitational acceleration affect the range. Extensions to more realistic scenarios involve considering drag, varying launch heights, and external forces, which are important for precise predictions in real-world applications.

---


```

If you want, I can help you generate a runnable Jupyter notebook version of this or provide a more detailed script with numerical integration to include drag or variable launch heights. Just let me know!
```
