<h1>ExpNo 1 :Developing AI Agent with PEAS Description</h1>
<h3>Name: POORNIMA J</h3>
<h3>Register Number: 212225040303</h3>


<h3>AIM:</h3>
<br>
<p>To find the PEAS description for the given AI problem and develop an AI agent.</p>
<br>
<h3>Theory</h3>
<h3>Medicine prescribing agent:</h3>
<p>Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.</p>
<hr>
<h3>PEAS DESCRIPTION:</h3>
<table>
  <tr>
    <td><strong>Agent Type</strong></td>
    <td><strong>Performance</strong></td>
     <td><strong>Environment</strong></td>
    <td><strong>Actuators</strong></td>
    <td><strong>Sensors</strong></td>
  </tr>
    <tr>
    <td><strong>Medicine prescribing agent</strong></td>
    <td><strong>Treating unhealthy, agent movement</strong></td>
     <td><strong>Rooms, Patient</strong></td>
    <td><strong>Medicine, Treatment</strong></td>
    <td><strong>Location, Temperature of patient</strong></td>
  </tr>
</table>
<hr>
<H3>DESIGN STEPS</H3>
<h3>STEP 1:Identifying the input:</h3>
<p>Temperature from patients, Location.</p>
<h3>STEP 2:Identifying the output:</h3>
<p>Prescribe medicine if the patient in a random has a fever.</p>
<h3>STEP 3:Developing the PEAS description:</h3>
<p>PEAS description is developed by the performance, environment, actuators, and sensors in an agent.</p>
<h3>STEP 4:Implementing the AI agent:</h3>
<p>Treat unhealthy patients in each room. And check for the unhealthy patients in random room</p>
<h3>STEP 5:</h3>
<p>Measure the performance parameters: For each treatment performance incremented, for each movement performance decremented</p>

<h3>Program:</h3>

```
import random

class MedicineAgent:
    def __init__(self):
        self.location = "Room A"
        self.performance = 0

    def act(self, environment):
        temp = environment[self.location]["temperature"]
        
        if temp > 98.5:
            print(f"Patient in {self.location} unhealthy ({temp:.1f}°F). Giving medicine.")
            self.performance += 10
            environment[self.location]["temperature"] = 98.0
        else:
            print(f"Patient in {self.location} healthy ({temp:.1f}°F).")

        self.location = "Room B" if self.location == "Room A" else "Room A"
        self.performance -= 1
        print(f"Moving to {self.location}. Performance: {self.performance}")
        print("-" * 30)

def main():
    environment = {
        "Room A": {"temperature": random.uniform(97.0, 102.0)},
        "Room B": {"temperature": random.uniform(97.0, 102.0)}
    }
    agent = MedicineAgent()

    print("Starting simulation.")
    print("-" * 30)

    for step in range(5):
        print(f"--- Step {step + 1} ---")
        agent.act(environment)
        
        random_room = random.choice(["Room A", "Room B"])
        environment[random_room]["temperature"] = random.uniform(99.0, 103.0)

    print("Simulation finished.")

if __name__ == "__main__":
    main()
```
<h3>Output:</h3>
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/1d9e687b-4400-492a-9d02-b4dd0a145b19" />
<img width="959" height="248" alt="image" src="https://github.com/user-attachments/assets/ff575cd8-b550-4c13-865c-b97f75532736" />

<h3>Result:</h3>

<p>Thus the developing of AI agent with PEAS description was implemented using python programming</p>


