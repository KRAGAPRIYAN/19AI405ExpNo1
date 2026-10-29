
# Experiment No. 1: Developing AI Agent with PEAS Description

**Name: K RAGAPRIYAN** 
**Register Number: 212225040323**

## AIM

To find the PEAS description for the given AI problem and develop an AI agent.

## THEORY

### Medicine Prescribing Agent

Such this agent prescribes medicine for fever (greater than 98.5 degrees) which we consider here as unhealthy, by the user temperature input, and another environment is rooms in the hospital (two rooms). This agent has to consider two factors one is room location and an unhealthy patient in a random room, the agent has to move from one room to another to check and treat the unhealthy person. The performance of the agent is calculated by incrementing performance and each time after treating in one room again it has to check another room so that the movement causes the agent to reduce its performance. Hence, agents prescribe medicine to unhealthy.

## PEAS DESCRIPTION

| Agent Type | Performance | Environment | Actuators | Sensors |
|---|---|---|---|---|
| Medicine prescribing agent | Treating unhealthy, agent movement | Rooms, Patient | Medicine, Treatment | Location, Temperature of patient |

## DESIGN STEPS

### STEP 1: Identifying the Input

Temperature from patients, Location.

### STEP 2: Identifying the Output

Prescribe medicine if the patient in a random has a fever.

### STEP 3: Developing the PEAS Description

PEAS description is developed by the performance, environment, actuators, and sensors in an agent.

### STEP 4: Implementing the AI Agent

Treat unhealthy patients in each room. And check for the unhealthy patients in random room.

### STEP 5: Measuring the Performance Parameters

For each treatment performance incremented, for each movement performance decremented.

## PYTHON CODE

```python
class MedicineAgent:
    def __init__(self):
        self.location = "Room A"
        self.performance = 0

    def act(self, environment):
        temperature = environment[self.location]["temperature"]

        print("\nChecking", self.location)
        print("Patient temperature:", temperature, "F")

        if temperature > 98.5:
            print("Fever detected. Simulating treatment.")
            self.performance += 10
        else:
            print("No fever detected.")

    def move(self):
        if self.location == "Room A":
            self.location = "Room B"
            self.performance -= 1
            print("Moving to Room B")

    def run(self, environment):
        self.act(environment)
        self.move()
        self.act(environment)

        print("\nFinal Performance Score:", self.performance)


environment = {
    "Room A": {"temperature": 99.5},
    "Room B": {"temperature": 98.0}
}

agent = MedicineAgent()
agent.run(environment)
```

## OUTPUT

![Experiment 1 Output](<Screenshot 2026-10-26 141835.png>)


## RESULT

Thus, the PEAS description was identified, and the Medicine Prescribing AI Agent was developed and executed successfully. The agent checked the temperature of patients in two rooms, simulated treatment when a fever was detected, and calculated the final performance score based on treatment and movement.

**Final Performance Score: 9**