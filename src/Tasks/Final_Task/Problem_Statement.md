<hr>
<h1 align="center">Final Task: Problem Statement</h1>
<hr>

## Objective

The final rescue operation requires the e-puck robot to execute a complete, multi-environment mission.

The robot will begin in the underground maintenance tunnel, follow the walls, decode ArUco markers to determine the rescue priority, and then transition into the open urban zone where it must follow lines, navigate intersections, and rescue all remaining survivors and train cars in the correct order.

---

## Mission Requirements

### Phase 1 - Underground Tunnel

- Follow the tunnel walls using proximity sensors.
- Detect and decode all ArUco markers.
- Store the complete rescue priority sequence.

### Phase 2 - Urban Recovery Zone

- Switch to line following.
- Navigate through intersections using the decoded ArUco instructions.
- Detect coloured shapes at each rescue point.
- Deliver survivors and supplies to the correct locations.
- Complete all objectives before time expires.

---

## Arena

The final task arena combines elements from all previous tasks.

It is divided into two connected environments:

- **Phase 1:** Narrow maintenance tunnel with walls and ArUco markers.
- **Phase 2:** Open urban grid with railway lines, intersections, coloured rescue points, and supply boxes.

---

## Scoring

The final score is composed of multiple components.

### Phase 1 Score

```text
Phase 1 Score = (ArUco Markers Decoded / Total Markers) x 20
```

### Phase 2 Score

```text
Phase 2 Score = (Objectives Completed / Total Objectives) x 60
```

### Time Bonus

```text
Time Bonus = (Remaining Time / Maximum Time) x 20
```

### Final Score

```text
Total Score = Phase 1 Score + Phase 2 Score + Time Bonus
```

> **Maximum Score: 100 Points**

---

## Expected Output

A successful controller should:

- Complete Phase 1 by decoding all ArUco markers.
- Transition cleanly to Phase 2.
- Follow all navigation instructions at intersections.
- Deliver every objective in the correct order.
- Complete the full mission before time expires.

### Demo Video

<center>

*The Final Task demo video will be added here once available.*

</center>

---

## Before You Submit

Before generating your submission, verify that:

- Both phases execute correctly without errors.
- All ArUco markers are decoded.
- All objectives are completed.
- `teaminfo.json` contains the correct Team ID.
- The submission package is generated successfully.
