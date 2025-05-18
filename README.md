
# 🚁 3D Quadrotor PD Control & Trajectory Generation – MATLAB

## 📌 Project Summary

This project simulates a 3D quadrotor and implements a full Proportional-Derivative (PD) control system in MATLAB to perform hover stabilization and trajectory tracking. A trajectory generator is also developed to create smooth paths through arbitrary waypoints using 7th-order minimum snap polynomials.

The controller is structured in nested loops: an outer-loop for position control and an inner-loop for attitude stabilization, reflecting real-world UAV control architecture.

---

## 🧠 Key Features

- **Full 3D dynamics simulation** (forces, moments, rigid body physics)
- **Nested PD controllers**:
  - Outer-loop (position): computes desired roll, pitch, and yaw
  - Inner-loop (attitude): computes control moments
- **Trajectory generation** via minimum snap interpolation (7th-order piecewise polynomials)
- **Support for custom and predefined trajectories**:
  - Straight-line
  - Helix
  - User-defined waypoints

---

## 📂 File Structure

```
📁 3D/
 ├─ controller.m         % Main PD controller logic
 ├─ traj_generator.m     % Computes smooth path through waypoints
 ├─ runsim.m             % Simulation entry point
 ├─ simulation_3d.m      % Core dynamics using ode45
 ├─ traj_line.p          % Predefined straight-line trajectory
 ├─ traj_helix.p         % Predefined helical trajectory
 └─ utils/               % Helper functions (rotations, plotting, etc.)
```

---

## ▶️ How to Run

1. Open MATLAB and set the working directory to the `3D/` folder.
2. Open `runsim.m` and set the desired trajectory handle:
   ```matlab
   trajhandle = @traj_line;    % Options: @traj_line, @traj_helix, @traj_generator
   ```
3. Run the simulation:
   ```matlab
   runsim
   ```

---

## 📊 Core Concepts Demonstrated

- Linearization of nonlinear dynamics around hover
- Attitude control using Z-X-Y Euler angle decomposition
- Position control using desired acceleration → desired angles
- Force-to-thrust and moment allocation to four rotors
- Polynomial trajectory fitting using matrix constraint solving

---

## 🛠 Skills Applied

- Control system design (nested PD loops)
- Rigid body dynamics modeling
- MATLAB scripting and simulation using `ode45`
- Minimum snap trajectory generation
- Modular code structure for controller and planner integration

---

## 📌 Notes

This project demonstrates a foundational flight control stack for quadrotors, integrating both motion planning and real-time control. The modular design and physical accuracy make it suitable as a learning tool or base for more advanced techniques like Model Predictive Control (MPC) or sensor-based feedback.

---

**Made with MATLAB | Simulating autonomous UAV control in 3D.**
