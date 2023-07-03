Most controllers should work out of the box because AGE have an internal mapping configuration that match with common used controllers in the market (the default mapping). If you can connect your controller to the headset (using Bluetooth for example) there is a great possibility that it works out of the box.

### The default mapping table

| MAME | Control | Behavior | Unity Path |
| --- | --- | --- | --- |
| JOYPAD_B | quest-b | button | `<XRController>{RightHand}/secondaryButton` |
| JOYPAD_B | gamepad-b | button | `<Gamepad>/buttonEast` |
| JOYPAD_B | quest-right-trigger | button | `<XRController>{RightHand}/triggerButton` |
| JOYPAD_B | keyboard-enter | button | `<keyboard>/enter` |
| JOYPAD_A | gamepad-a | button | `<Gamepad>/buttonSouth` |
| JOYPAD_A | quest-a | button | `<XRController>{RightHand}/primaryButton` |
| JOYPAD_X | gamepad-x | button | `<Gamepad>/buttonWest` |
| JOYPAD_X | quest-x | button | `<XRController>{LeftHand}/primaryButton` |
| JOYPAD_Y | gamepad-y | button | `<Gamepad>/buttonNorth` |
| JOYPAD_Y | quest-y | button | `<XRController>{LeftHand}/secondaryButton` |
| JOYPAD_START | gamepad-start | button | `<Gamepad>/start` |
| JOYPAD_START | quest-start | button | `<XRController>{LeftHand}/menuButton` |
| JOYPAD_SELECT | gamepad-select | button | `<Gamepad>/select` |
| JOYPAD_SELECT | quest-select | button | `<XRController>{RightHand}/menuButton` |
| JOYPAD_UP | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| JOYPAD_UP | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| JOYPAD_DOWN | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| JOYPAD_DOWN | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| JOYPAD_LEFT | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| JOYPAD_LEFT | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| JOYPAD_RIGHT | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| JOYPAD_RIGHT | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| JOYPAD_L | quest-left-trigger | button | `<XRController>{LeftHand}/triggerButton` |
| JOYPAD_L | gamepad-left-trigger | button | `<Gamepad>/leftTrigger` |
| JOYPAD_R | quest-right-trigger | button | `<XRController>{RightHand}/triggerButton` |
| JOYPAD_R | gamepad-right-trigger | button | `<Gamepad>/rightTrigger` |
| JOYPAD_L2 | quest-left-grip | button | `<XRController>{LeftHand}/gripButton` |
| JOYPAD_L2 | gamepad-left-bumper | button | `<Gamepad>/leftShoulder` |
| JOYPAD_R2 | quest-right-grip | button | `<XRController>{RightHand}/gripButton` |
| JOYPAD_R2 | gamepad-right-bumper | button | `<Gamepad>/rightShoulder` |
| JOYPAD_R3 | quest-right-thumbstick-press | button | `<XRController>{RightHand}/thumbstickClicked` |
| JOYPAD_R3 | gamepad-right-thumbstick-press | button | `<Gamepad>/rightStickPress` |
| EXIT | quest-left-grip | button | `<XRController>{LeftHand}/gripButton` |
| EXIT | gamepad-left-bumper | button | `<Gamepad>/leftShoulder` |
| EXIT | keyboard-esc | button | `<keyboard>/escape` |
| INSERT | gamepad-select | button | `<Gamepad>/select` |
| MOUSE_X | quest-right-thumbstick | axis | `<XRController>{RightHand}/Primary2DAxis` |
| MOUSE_X | gamepad-right-thumbstick | axis | `<Gamepad>/rightStick` |
| MOUSE_Y | quest-right-thumbstick | axis | `<XRController>{RightHand}/Primary2DAxis` |
| MOUSE_Y | gamepad-right-thumbstick | axis | `<Gamepad>/rightStick` |
| MOUSE_LEFT | quest-b | button | `<XRController>{RightHand}/secondaryButton` |
| MOUSE_LEFT | gamepad-b | button | `<Gamepad>/buttonEast` |
| MOUSE_RIGHT | quest-a | button | `<XRController>{RightHand}/primaryButton` |
| MOUSE_RIGHT | gamepad-a | button | `<Gamepad>/buttonSouth` |
| MOUSE_MIDDLE | quest-x | button | `<XRController>{LeftHand}/primaryButton` |
| MOUSE_MIDDLE | gamepad-x | button | `<Gamepad>/buttonWest` |
| MOUSE_WHEELUP | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| MOUSE_WHEELUP | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| MOUSE_WHEELDOWN | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| MOUSE_WHEELDOWN | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| MOUSE_HORIZ_WHEELUP | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| MOUSE_HORIZ_WHEELUP | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| MOUSE_HORIZ_WHEELDOWN | quest-left-thumbstick | axis | `<XRController>{LeftHand}/Primary2DAxis` |
| MOUSE_HORIZ_WHEELDOWN | gamepad-left-thumbstick | axis | `<Gamepad>/leftStick` |
| MOUSE_BUTTON_4 | quest-left-thumbstick-press | button | `<XRController>{LeftHand}/thumbstickClicked` |
| MOUSE_BUTTON_4 | gamepad-left-thumbstick-press | button | `<Gamepad>/leftStickPress` |
| MOUSE_BUTTON_5 | quest-right-thumbstick-press | button | `<XRController>{RightHand}/thumbstickClicked` |
| MOUSE_BUTTON_5 | gamepad-right-thumbstick-press | button | `<Gamepad>/rightStickPress` |


