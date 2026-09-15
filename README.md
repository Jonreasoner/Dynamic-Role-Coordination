
ABSTRACT

Multi-robot teams operating in adversarial and communication-denied environments must coordinate despite limited information about both the environment and the performance of their teammates. We present a decentralized framework for communication-free pursuit--evasion in which robots dynamically adapt their roles, coordinating between active pursuit and auxiliary tasks as the situation evolves. Rather than relying on fixed role assignments, each robot infers evader intent, teammate behavior, and team needs from local observations and continuously reconfigures its role in response to changes in the environment, evader behavior, and teammate performance. A second-order Theory-of-Mind active-inference planner reasons about how candidate actions will affect teammates' beliefs and selects trajectories that are both task-directed and informative, enabling implicit coordination without explicit communication. Across 720 randomized trials with three- and four-robot teams, three evader policies, and environments with and without obstacles, our method achieves up to 98.9\% capture rate, outperforming lower-order reasoning and reinforcement-learning and geometric baselines. Simulations and laboratory experiments further demonstrate online role adaptation and team reconfiguration in pursuit--evasion scenarios, including settings with auxiliary tasks and robot failures. 



EXAMPLE SIMULATIONS

In a simple pursuit-evasion scenario, our approach outperforms baseline reinforcement and geometric based methods by using our approach's combination of latent intent prediction and higher-order reasoning. Robots adapt their role positions as evader motion increases the team's confidence regarding which target it is attempting to reach.
<img width="850" height="850" alt="website_3_robot_ours" src="https://github.com/user-attachments/assets/9fbf31b6-6956-422c-8aa4-2bbd548f5907" />


Baseline reinforcement learning method, using a proximal policy optimization is unable to capture the evading robot.


Baseline geometric method is unable to capture the evading robot.
<img width="750" height="650" alt="website_3_robot_voronoi" src="https://github.com/user-attachments/assets/551e9dbd-63df-4a96-9a47-0403bb246ff1" />



"Broken Robot" scenario. In this case, r2 suffers a hardware failure during the mission. Without communication, the team detects that r2 has deviated from expected behavior and reconfigures the team roles to ensure capture of the evader.

<img width="850" height="850" alt="website_broken" src="https://github.com/user-attachments/assets/e21b0b5b-1301-46af-8dff-9d8e2221b2db" />


