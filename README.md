# TRAFFIC-FSM
This is a fully interactive Traffic Signal Controller built using HTML, CSS, and JavaScript, implementing a Finite State Machine (FSM) model. Designed as part of a project for the Theory of Computation subject, it simulates real-world traffic signal behavior through state transitions and queue-based event processing.

# Technologies Used & Their Contribution

* **HTML5**

  * Structures the entire webpage.
  * Defines containers for lights, controls, inputs, and logs.

* **CSS3**

  * Provides responsive and modern UI styling using:

    * Grid Layouts (`.main-grid`, `.status-grid`)
    * Transitions/Animations for lights
    * Themed gradients for a visually appealing look
  * Makes the simulation interactive and user-friendly.

* **JavaScript (Vanilla JS)**

  * Implements **Finite State Machine (FSM)** logic.
  * Handles:

    * Command parsing (`g`, `y`, `r`, `e`, `p1–p99`)
    * Command queuing and validation
    * Emergency logic, pedestrian crossing logic
    * Live UI updates, including:

      * Activating lights
      * Logging system
      * State tracking (`IDLE`, `GREEN_LIGHT`, etc.)

* **DOM Manipulation**

  * JavaScript dynamically updates HTML elements like:

    * `#currentState`
    * `.log-container`
    * `.light.active/off`

  # Instructions to Use the Website (How-To)

* **Basic Light Controls**

  * Click buttons:

    * **Green (G)** → `g`
    * **Yellow (Y)** → `y`
    * **Red (R)** → `r`
    * **Emergency (E)** → `e`
  * These are added to a request queue and processed sequentially every 2 seconds.

* **Pedestrian Crossing**

  * Enter a number (1–99) in the input field under *Pedestrian Request*.
  * Click **“Request Crossing”** → adds `pX` (e.g., `p5`) to queue.

* **Custom Command Sequence**

  * Type a sequence of commands (e.g., `g y r p5 e`) in the text input.
  * Click **"Send Sequence"**.
  * All commands are parsed and queued for execution.

* **Reset System**

  * Click the **“Reset System”** button.
  * All lights and queues are cleared, and the system returns to `IDLE`.

* **Keyboard Shortcuts**

  * Use keys `G`, `Y`, `R`, and `E` to simulate commands directly without clicking.

---

# FSM Logic Summary

* States: `IDLE`, `GREEN_LIGHT`, `YELLOW_LIGHT`, `RED_LIGHT`, `PEDESTRIAN_GREEN`, `EMERGENCY_RESPONSE`
* Each command triggers a state transition.
* The FSM queues and executes commands one at a time (unless emergency overrides).
* Emergency (`e`) clears queue and halts normal processing.
