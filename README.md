# Wave Application 
[Paper](https://ieeexplore.ieee.org/document/10396173)


The Wave application, a graphical user interface (GUI) program built using Python. The Wave application provides functionality related to computer vision, webcam control, and menu settings.



https://github.com/17Swagat/wave/assets/72545910/7fc69810-2d12-438d-bcfe-24005815cde8



## Table of Contents

- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Application Structure](#application-structure)
- [License](#license)

## Dependencies

Before running the Wave application, ensure you have the dependencies as specified in the `requirements.txt` file

## Installation

To install the required dependencies, you can use the following command:

```bash
pip install -r requirements.txt
```

Make sure you have [pip](https://pip.pypa.io/en/stable/installation/) installed before running the above command.

## Usage

To use the Wave application, follow these steps:

1. Import the required modules:

    ```python
    import customtkinter as ctk
    from appsettings import *
    from menu import Menu
    from vid_nd_control import WebCamView
    from appsettings import *
    ```

2. Create an instance of the `App` class:

    ```python
    if __name__ == '__main__':
        App()
    ```

3. Run the application.

## Application Structure

### `App` Class

The `App` class is the main class of the Wave application. It inherits from `customtkinter.CTk` and initializes the GUI, layout, and various settings.

#### Initialization

- Initializes `customtkinter.CTk` settings.
- Sets the window size and title.
- Configures the layout of the application.

#### Layout

- Configures the layout using the `columnconfigure` and `rowconfigure` methods.

#### Computer Vision and Webcam Control

- Initializes and sets up the `WebCamView` class for computer vision and webcam control.

#### Menu

- Initializes and sets up the `Menu` class for handling menu settings.

#### Main Loop

- Runs the main event loop using `self.mainloop()`.

#### Parameter Initialization

- Initializes Tkinter variables for video control, hand landmark recognition, PC control, and mouse smoothness.

### `init_parameters` Method

- Initializes Tkinter variables for the application.




# ComponentFrame and Panels

This is the README file for the `ComponentFrame`, `SliderPanel`, and `OnOffSwitchPanel` classes. These components are part of a Python application built using the `customtkinter` library. The components provide a user interface for sliders and on/off switches with customizable styles.

## Table of Contents
- [Usage](#usage)
- [Component Structure](#component-structure)
- [License](#license)


## Usage

To use the `ComponentFrame`, `SliderPanel`, and `OnOffSwitchPanel` classes, follow these steps:

1. Import the required modules:

    ```python
    import customtkinter as ctk
    from appsettings import *
    ```

2. Create an instance of the desired component:

    ```python
    # Example for SliderPanel
    slider_panel = SliderPanel(parent, text, data_var, min_value, max_value)
    ```

    ```python
    # Example for OnOffSwitchPanel
    on_off_panel = OnOffSwitchPanel(parent, text, showVideo, showHandlandmarks, control_pc)
    ```

3. Use the component instance in your application.

## Component Structure

### `ComponentFrame` Class

The `ComponentFrame` class is a customized frame based on `customtkinter.CTkFrame`. It provides a consistent look for the components.

### `SliderPanel` Class

The `SliderPanel` class extends `ComponentFrame` and is designed to create a panel with a slider and corresponding numerical display.

#### Initialization

- Initializes the layout and sets up the slider and labels.

#### `update_text` Method

- Updates the numerical display based on the slider value.

### `OnOffSwitchPanel` Class

The `OnOffSwitchPanel` class extends `ComponentFrame` and creates a panel with on/off switches for various functionalities.

#### Initialization

- Initializes the layout and sets up on/off switches for webcam, hand landmarks, and PC control.

# Menu and Control Frames

This is the README file for the `Menu`, `ControlsFrame`, and `HelpFrame` classes. These classes are part of a Python application built using the `customtkinter` library. The components provide a menu structure, controls frame, and a help frame for the application.

## Table of Contents

- [Dependencies](#dependencies)
- [Installation](#installation)
- [Usage](#usage)
- [Component Structure](#component-structure)
- [License](#license)

## Usage

To use the `Menu`, `ControlsFrame`, and `HelpFrame` classes, follow these steps:

1. Import the required modules:

    ```python
    import customtkinter as ctk
    from components import *
    ```

2. Create an instance of the `Menu` class:

    ```python
    menu = Menu(parent, mouse_smoothness, video_on_off, show_handlandmarks, pccontrol)
    ```

3. Use the menu instance in your application.

## Component Structure

### `Menu` Class

The `Menu` class extends `customtkinter.CTkTabview` and provides a tabbed menu structure for the application.

#### Initialization

- Initializes the menu with two tabs: 'Controls' and 'Help'.
- Sets up the `ControlsFrame` and `HelpFrame` as content for the respective tabs.

### `ControlsFrame` Class

The `ControlsFrame` class extends `customtkinter.CTkFrame` and creates a frame containing on/off switches, a slider, and a theme change option.

#### Initialization

- Initializes the layout and sets up on/off switches and sliders for controlling video, hand landmarks, and PC control.
- Adds a theme change option.

### `HelpFrame` Class

The `HelpFrame` class extends `customtkinter.CTkFrame` and creates a frame for displaying help-related content.

#### Initialization

- Initializes the layout with a red background (for illustration purposes).

# WebcamView

This is the README file for the `WebCamView` class. This class is part of a Python application using the `customtkinter`, `cv2`, `mediapipe`, `PIL`, `keyboard`, and other libraries. It provides a webcam view with hand landmark detection, gesture recognition, and PC control functionalities.

## Table of Contents

- [Usage](#usage)
- [Class Structure](#class-structure)
- [License](#license)



## Usage

To use the `WebCamView` class, follow these steps:

1. Import the required modules:

    ```python
    from tkinter import Canvas
    import cv2 as cv
    from appsettings import *
    import mediapipe as mp
    import pickle
    import numpy as np
    from PIL import Image, ImageTk
    import keyboard
    import time
    ```

2. Create an instance of the `WebCamView` class:

    ```python
    webcam_view = WebCamView(parent, mouse_smoothness, video_on_off, handlandmarks_on_off, pccontrol_on_off)
    ```

3. Use the `webcam_view` instance in your application.

## Class Structure

### `WebCamView` Class

The `WebCamView` class extends the `Canvas` widget and provides a webcam view with hand landmark detection, gesture recognition, and PC control functionalities.

#### Initialization

- Initializes the webcam view with specified parameters such as `mouse_smoothness`, `video_on_off`, `handlandmarks_on_off`, and `pccontrol_on_off`.

#### `update_frame` Method

- Continuously updates the webcam frame, performs hand landmark detection, and recognizes gestures.
- Controls the visibility of the webcam view based on the `video_on_off` variable.

#### `check_hands` Method

- Uses the `mediapipe` library to process the webcam frame and detect hand landmarks.
- Performs gesture recognition and PC control based on the detected hand landmarks.

#### `perform_function` Method

- Placeholder method for performing actions based on the predicted hand sign.

# App Settings

This is the README file for the application settings module. The settings include configuration parameters for the application, such as window dimensions, mouse control options, themes, and gesture recognition mappings.

## Table of Contents

- [Configuration Parameters](#configuration-parameters)
- [Colors and Fonts](#colors-and-fonts)
- [Temporary Variables](#temporary-variables)
- [License](#license)

## Configuration Parameters

### Video and Handlandmarks Control

- `SHOW_VIDEO`: Determines whether the webcam video is displayed (True/False).
- `SHOW_HANDLANDMARKS`: Determines whether hand landmarks are shown on the video (True/False).
- `FUNCTIONING_ON`: Indicates whether the application's functionalities are turned on or off (True/False).

### Window Dimensions

- `WINDOW_HEIGHT`: Height of the application window.
- `WINDOW_WIDTH`: Width of the application window.
- `SCREEN_WIDTH`: Width of the user's screen.
- `SCREEN_HEIGHT`: Height of the user's screen.

### Theme

- `THEME`: Dictionary containing theme options, including 'Dark' and 'Light'.

### Mouse Control

- `DEFAULT_MOUSE_SMOOTHNESS`: Default smoothness factor for mouse movement.

### Gesture Recognition Mapping

- `HANDSIGN`: Dictionary mapping gesture labels to corresponding actions.

### Webcam Frame Reduction

- `FRAME_REDUCTION`: Value used for frame reduction during calculations.

## Colors and Fonts

- `BACKGROUND_COLOR`: Background color of the application.
- `WHITE`: White color.
- `GRAY`: Gray color.
- `BLUE`: Blue color.
- `DARK_GREY`: Dark grey color.
- `CLOSE_RED`: Close red color.
- `SLIDER_BG`: Slider background color.
- `FONT_1`: Font family for certain components.
- `FONT_2`: Another font family.
- `BUTTON_FONT_SIZE`: Font size for buttons.

## Temporary Variables

- `plocX, plocY`: Previous (X, Y) coordinates of the mouse pointer.
- `clocX, clocY`: Current (X, Y) coordinates of the mouse pointer.

## License

This project is licensed under the [MIT License](LICENSE).
