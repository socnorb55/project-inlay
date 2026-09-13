# Hardware Specification

## 1. Purpose

Project-Inlay is a wired, programmable hardware control surface
designed as a product-quality embedded systems learning project.

The controller design prioritizes:
- precision
- reliability
- expandability
- tactile interaction
- maintainability
- reproducibility
- source available hardware and software

## 2. Product Definition

The controller shall contain:

- 24 mechanical keys arranged as a 4×6 matrix
- 1 master rotary encoder
- 2 standard rotary encoders
- 1 eight-position rotary selector
- 2 toggle switches
- 1 OLED display
- RGB illumination around rotary controls
- haptic feedback on rotary controls
- USB-C connectivity
- external non-volatile macro storage
- expansion connector
- custom PCB
- custom enclosure

## 3. Input Requirements

### 3.1 Keys

#### Requirements
- 24 keys
- 4×6 matrix
- Individually addressable by firmware
- Debounced in firmware
- Suitable for QMK

#### Key Matrix

Key positions will be defined as:

K00 K01 K02 K03 K04 K05
K10 K11 K12 K13 K14 K15
K20 K21 K22 K23 K24 K25
K30 K31 K32 K33 K34 K35

#### Key Behavior

Supported Actions:

- Press
- Release

A key press shall generate the configured key action and a release shall terminate the corresponding action where applicable

#### Debouncing

Key press shall not result in multiple unintended key events

Key debouncing shall be handled by firmware

#### Layers

All keys shall operate according to the current layer

Keys may have different functions on different layers

Example:

- Layer 0:
    - K00 -> Q
    - K01 -> W
    - K02 -> E
- Layer 1:
    - K00 -> 1
    - K01 -> 2
    - K02 -> 3

#### Key Actions

All keys should be capable of triggering standard QMK/Vial actions:

- Keyboard Keys
- Modifiers
- Modifier + Key Combination
- Consumer/Media Keys
- System Keys (Where Supported)
- Mouse Buttons (Where Supported)
- Macros

#### Chorded Input

Multiple key may be pressed simultaneously

The firmware shall correctly distinguish simultaneous key
presses within the limitations of the selected matrix hardware
and switch technology

#### Repeat Behavior

Keys assigned to normal keyboard actions shall support normal
USB HID key-repeat behavior through the host operating system

The device shall not implement unnecessary custom repeat
behavior unless explicitly required

### 3.2 Master Encoder

- Rotary input
- Push-button input
- Haptic feedback
- RGB indicator
- High-quality mechanical construction

### 3.3 Standard Encoders

- 2 rotary inputs
- Push-button input
- Haptic feedback
- RGB indicator
- High-quality mechanical construction

### 3.4 Layer Selector

- 8 discrete positions
- Physically selects the active layer
- Position must be readable by firmware
- Each position must provide deterministic input

### 3.5 Toggle Switches

- 2 independent inputs
- Firmware-readable
- Programmable behavior

## 4. Feedback Requirements

### 4.1 Haptics

Haptic feedback shall be available for all rotary controls.

The firmware shall be capable of generating distinct feedback
events such as:

- encoder detent
- button press
- layer change
- macro activation
- macro completion
- error/warning

Haptic behavior must be software-controlled.

### 4.2 RGB

RGB feedback shall provide contextual information.

The firmware shall be capable of representing:

- active layer
- control state
- macro state
- warnings/errors
- user-defined status

### 4.3 OLED

The OLED shall provide contextual device information.

At minimum it should be capable of displaying:

- active layer
- active profile/state
- encoder function
- relevant parameter/value

## 5. Storage Requirements

The controller shall provide persistent external storage
for a substantially larger macro library than would normally
be practical using only MCU internal memory.

Storage shall:

- survive power loss
- be firmware-accessible
- be replaceable if practical
- have a documented data format
- support future expansion of the macro system

## 6. Connectivity

### USB

- USB-C connector
- Wired operation for V1
- USB HID support
- Firmware update capability

### Expansion

The device shall provide an expansion connector exposing
useful MCU peripherals.

Candidate signals:

- 3.3 V
- GND
- GPIO
- I²C
- SPI
- UART
- ADC where practical

## 7. Firmware

The controller firmware shall use:

- QMK
- Vial as the official configuration interface

The hardware should remain as close as practical to
upstream QMK architecture.

Custom hardware functionality should be isolated into
dedicated drivers/modules rather than unnecessary QMK core
modifications.

## 8. Electrical Requirements

The design shall:

- operate from USB power
- use appropriate power regulation
- protect the USB interface where appropriate
- provide appropriate decoupling
- provide appropriate current limiting for RGB
- provide appropriate driver circuitry for haptics
- remain within MCU GPIO/current limits
- provide test points for important power and communication rails

## 9. Mechanical Requirements

The final device shall:

- use a custom enclosure
- use a custom PCB
- have a rigid construction
- provide appropriate mounting for the PCB
- provide appropriate mounting for haptic actuators
- provide clearance for all controls
- provide access to USB-C
- provide access to the expansion connector

## 10. Manufacturing Requirements

The design shall be manufacturable using commercially
available PCB fabrication and assembly services.

All production-critical files shall be included in the repository:

- schematic
- PCB
- footprints
- BOM
- Gerbers
- pick-and-place data where applicable
- assembly drawings
- mechanical CAD
- manufacturing documentation

## 11. Source Available / Reproducibility

A person with access to the repository shall have everything
required to reproduce the controller.

No proprietary or private design files shall be required.

Editable source files shall be committed alongside
generated manufacturing/release artifacts.

## 12. Constraints

The controller shall be:

- wired
- USB-C
- QMK-based
- Vial-configurable
- custom PCB
- custom enclosure

The controller shall not require:

- wireless connectivity
- a custom desktop application
- cloud services
- proprietary configuration software

## 13. Acceptance Criteria

The hardware requirements are considered satisfied when:

[checklist]

## 14. Open Design Decisions

Items not yet finalized:

- MCU
- exact encoder models
- haptic actuator model
- haptic driver
- OLED model
- RGB implementation
- external flash capacity
- expansion connector
- exact USB protection
- PCB layer count
- enclosure manufacturing method