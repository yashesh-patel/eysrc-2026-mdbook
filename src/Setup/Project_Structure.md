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
├── Eval/
├── protos/
└── worlds/
```

---

## Directory Description

### assets/

Contains models, textures, images, and other resources used by the simulation.

> Participants generally do not need to modify these files.

---

### controllers/

Contains all robot controllers used during the simulation.

```text
controllers/
├── e-puck/
│   └── e-puck.py
└── my_supervisor/
```

- **e-puck.py** → Main controller to be implemented by participants.
- **my_supervisor/** → Supervisor controller responsible for scoring, timing, and task management.

---

### Eval/

Contains the evaluation scripts used for validating submissions.

Typical contents include:

- Evaluator
- Submission generator
- Encryption keys

> Do not modify these files.

---

### protos/

Contains custom robot and arena definitions used by Webots.

These files define the objects that appear in the simulation.

---

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
- Avoid modifying supervisor or evaluation files.
- Verify that your solution works before generating the submission package.