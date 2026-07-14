# Project Structure

---

## Overview

Each task package follows a common directory structure. Understanding this layout will help you quickly locate the files required for development and testing.

```text
Task_X/
├── assets/
├── controllers/
│   ├── e-puck/
│   └── my_supervisor/
├── protos/
└── worlds/
```

---

## Directory Description

### controllers/

Contains all robot controllers used during the simulation.

```text
controllers/
├── e-puck/
│   └── e-puck.py
└── my_supervisor/
```

- **e-puck.py** → Main controller to be implemented by participants.

### worlds/

Contains the Webots simulation world.

Example:

```text
worlds/
└── task_X.wbt
```

Open this file in Webots to start the simulation.

---

## Which Files Should You Modify?

For most tasks, you only need to edit:

```text
controllers/
└── e-puck/
    └── e-puck.py
```

All other files are provided to support the simulation and evaluation.

---

## Development Workflow

```text
Open World
      │
      ▼
Edit e-puck.py
      │
      ▼
Run Simulation
      │
      ▼
Test Controller
      │
      ▼
Generate Submission
```

---

## Best Practices

- Keep your controller modular by using functions.
- Test frequently after making changes.
- Verify that your solution works before generating the submission package.