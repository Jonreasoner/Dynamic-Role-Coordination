# Communication-Free Role Adaptation for Multi-Robot Pursuit-Evasion

## Abstract

Multi-robot teams operating in adversarial and communication-denied environments must coordinate despite limited information about both the environment and the performance of their teammates. We present a decentralized framework for communication-free pursuit-evasion in which robots dynamically adapt their roles, coordinating between active pursuit and auxiliary tasks as the situation evolves.

Rather than relying on fixed role assignments, each robot infers evader intent, teammate behavior, and team needs from local observations, continuously reconfiguring its role in response to changes in the environment, evader behavior, and teammate performance. A second-order Theory-of-Mind active-inference planner reasons about how candidate actions will affect teammates' beliefs and selects trajectories that are both task-directed and informative, enabling implicit coordination without explicit communication.

Across 720 randomized trials with three- and four-robot teams, three evader policies, and environments with and without obstacles, our method achieves capture rates of up to 98.9%, outperforming lower-order reasoning approaches and reinforcement-learning and geometric baselines. Simulations and laboratory experiments further demonstrate online role adaptation and team reconfiguration in pursuit-evasion scenarios, including settings with auxiliary tasks and robot failures.

---

## Example Simulations

### Pursuit-Evasion Baseline Comparison

We first evaluate the proposed method in standard pursuit-evasion scenarios and compare its performance against reinforcement-learning and geometric baselines. The examples below illustrate representative behaviors for three- and four-robot teams.

#### Three-Robot Scenario

**Our Approach**

Our method combines latent-intent prediction with higher-order reasoning to coordinate the pursuers without explicit communication. As observations of the evader reduce uncertainty about its intended goal, the robots adapt their roles and interception positions to maintain an effective capture strategy.

<img width="750" height="750" alt="Three-robot pursuit-evasion scenario using our approach" src="https://github.com/user-attachments/assets/9fbf31b6-6956-422c-8aa4-2bbd548f5907" />

**PPO Baseline**

A reinforcement-learning baseline based on Proximal Policy Optimization (PPO) is unable to successfully coordinate the pursuers and capture the evader in this scenario.

<img width="800" height="750" alt="Three-robot pursuit-evasion scenario using PPO baseline" src="https://github.com/user-attachments/assets/b9e92006-ae39-4c65-a155-c962ff381749" />

**Voronoi Baseline**

The geometric Voronoi baseline is also unable to capture the evader in this scenario.

<img width="800" height="750" alt="Three-robot pursuit-evasion scenario using Voronoi baseline" src="https://github.com/user-attachments/assets/551e9dbd-63df-4a96-9a47-0403bb246ff1" />

---

#### Four-Robot Scenario

The proposed framework extends naturally to larger teams. The following examples show representative behavior for a four-robot pursuit team using our method and the two baseline controllers.

**Our Approach**

The robots continuously adapt their roles based on the inferred evader objective and the observed behavior of their teammates.

<img width="750" height="750" alt="Four-robot pursuit-evasion scenario using our approach" src="https://github.com/user-attachments/assets/f8917797-75c4-4b75-aa98-ad37fe98ec53" />

**Voronoi Baseline**

<img width="800" height="800" alt="Four-robot pursuit-evasion scenario using Voronoi baseline" src="https://github.com/user-attachments/assets/426db504-aff5-470e-8bc8-6ca3287666bb" />

**PPO Baseline**

<img width="750" height="750" alt="website_4_robot_ppo" src="https://github.com/user-attachments/assets/8c39693e-db03-4ccf-a1d7-024c5d1bd68a" />

---

## Pursuit-Evasion with Auxiliary Tasks and Robot Failures

Beyond standard pursuit-evasion, the framework supports dynamic role adaptation when the team must simultaneously respond to additional mission requirements or changes in robot availability. In these scenarios, the robots must determine which agents are required for interception and which can be reassigned to other objectives, all without explicit communication.

### Auxiliary-Task Scenario

Here, the team must both capture the evader and complete an auxiliary task. As the robots' estimate of the evader's intended goal evolves, the team reconfigures its roles online. Robot \(r_1\) is ultimately released from the capture team and assigned to the auxiliary task while the remaining robots continue the interception.

<img width="750" height="750" alt="Online role adaptation with an auxiliary task" src="https://github.com/user-attachments/assets/43b0bddc-79c4-4460-bcff-576123915df3" />

### Robot-Failure Scenario

In this experiment, robot \(r_2\) experiences a hardware failure during the mission. Without receiving an explicit failure notification, the remaining robots detect that \(r_2\)'s observed motion is inconsistent with its expected behavior and update their beliefs accordingly. The team then reconfigures its roles online so that the remaining operational robots can maintain the capture strategy.

<img width="750" height="750" alt="Online team reconfiguration following a robot failure" src="https://github.com/user-attachments/assets/e21b0b5b-1301-46af-8dff-9d8e2221b2db" />































-----------

------------

-----------

ABSTRACT

Multi-robot teams operating in adversarial and communication-denied environments must coordinate despite limited information about both the environment and the performance of their teammates. We present a decentralized framework for communication-free pursuit--evasion in which robots dynamically adapt their roles, coordinating between active pursuit and auxiliary tasks as the situation evolves. Rather than relying on fixed role assignments, each robot infers evader intent, teammate behavior, and team needs from local observations and continuously reconfigures its role in response to changes in the environment, evader behavior, and teammate performance. A second-order Theory-of-Mind active-inference planner reasons about how candidate actions will affect teammates' beliefs and selects trajectories that are both task-directed and informative, enabling implicit coordination without explicit communication. Across 720 randomized trials with three- and four-robot teams, three evader policies, and environments with and without obstacles, our method achieves up to 98.9\% capture rate, outperforming lower-order reasoning and reinforcement-learning and geometric baselines. Simulations and laboratory experiments further demonstrate online role adaptation and team reconfiguration in pursuit--evasion scenarios, including settings with auxiliary tasks and robot failures. 



EXAMPLE SIMULATIONS

PURSUIT-EVASION GAMES FOR BASELINE COMPARISON

3 ROBOT SCENARIO:

3 ROBOT SCENARIO - Our approach. In a simple pursuit-evasion scenario, our approach outperforms baseline reinforcement and geometric based methods by using our approach's combination of latent intent prediction and higher-order reasoning. Robots adapt their role positions as evader motion increases the team's confidence regarding which target it is attempting to reach.

<img width="850" height="850" alt="website_3_robot_ours" src="https://github.com/user-attachments/assets/9fbf31b6-6956-422c-8aa4-2bbd548f5907" />


3 ROBOT SCENARIO - Baseline reinforcement learning method, using a proximal policy optimization (PPO) is unable to capture the evading robot.

<img width="750" height="650" alt="website_3_robot_ppo" src="https://github.com/user-attachments/assets/b9e92006-ae39-4c65-a155-c962ff381749" />

3 ROBOT SCENARIO - Baseline geometric method (Voronoi) is unable to capture the evading robot.

<img width="750" height="650" alt="website_3_robot_voronoi" src="https://github.com/user-attachments/assets/551e9dbd-63df-4a96-9a47-0403bb246ff1" />

4 ROBOT SCENARIO:

Results show that our approach improves performance in teams of all sizes, with one representative case shown here.

4 ROBOT SCENARIO - Our approach

<img width="850" height="850" alt="website_4_robot_ours" src="https://github.com/user-attachments/assets/f8917797-75c4-4b75-aa98-ad37fe98ec53" />

4 ROBOT SCENARIO - Voronoi baseline

<img width="750" height="650" alt="website_4_robot_voronoi" src="https://github.com/user-attachments/assets/426db504-aff5-470e-8bc8-6ca3287666bb" />

4 ROBOT SCENARIO - PPO baseline

<img width="750" height="650" alt="website_4_robot_ppo" src="https://github.com/user-attachments/assets/8998a029-7e8b-48fb-8fe1-cb67fa672292" />



PURSUIT-EVASION WITH AUXILIARY TASKS AND HARDWARE FAILURES


In addition to simple pursuit-evasion games, our approach is designed to handle more complex scenarios, such as pursuit-evasion games with additional auxiliary tasks in the environment that should be completed by the team of robots. In these scenarios, the robots much coordinate which role they will take to ensure that capture of the evader is performed and any auxiliary tasks are completed, all without communication. 

In this case, the team reconfigures their roles online as their prediction of the evader's target shifts, leaving r1 to complete the auxiliary task

<img width="1080" height="1080" alt="Adobe Express - website_adaptive_edited" src="https://github.com/user-attachments/assets/43b0bddc-79c4-4460-bcff-576123915df3" />





"Broken Robot" scenario. In this case, r2 suffers a hardware failure during the mission. Without communication, the team detects that r2 has deviated from expected behavior and reconfigures the team roles to ensure capture of the evader.

<img width="850" height="850" alt="website_broken" src="https://github.com/user-attachments/assets/e21b0b5b-1301-46af-8dff-9d8e2221b2db" />


