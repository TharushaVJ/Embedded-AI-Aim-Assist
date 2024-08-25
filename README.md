# FPS Enemy Detection and Aim Assist System

## Project Overview

This project aims to create an automated aim assist system for an FPS game ("V") by using a TensorFlow object detection model to identify enemies in real-time. The system runs on a Raspberry Pi 4, with the aid of a Coral Edge TPU USB Accelerator for efficient processing. Once enemies are detected, the system uses an Arduino Leonardo to adjust mouse movements accordingly, providing an automated aiming mechanism.

## Hardware Components

- **Raspberry Pi 4**: The main processing unit where the TensorFlow model runs.
- **Coral Edge TPU USB Accelerator**: Accelerates the object detection process on the Raspberry Pi.
- **Arduino Leonardo**: Acts as a USB mouse, receiving input from the Raspberry Pi and translating it into mouse movements.
- **Capture Card**: Used to capture the screen output of the game for real-time processing. (might use a HDMI to CSI2 adapter instead)
- **Level Shifter**: Used to connect the Arduino Leonardo which has 5V GPIO pins and the Raspberry Pi 4 which has 3.3V GPIO pins theough I2C.

## Software Components

- **TensorFlow**: Used for training and running the object detection model.
- **Python**: The primary programming language used for the data processing and model inference.
- **Arduino IDE**: For programming the Arduino Leonardo to spoof the mouse.

## Project Structure (Temporary)

- [`/models/`](https://github.com/TharushaVJ/AI-Aim-Assist/tree/main/models): Contains the trained TensorFlow object detection models.
- [`/scripts/`](https://github.com/TharushaVJ/AI-Aim-Assist/tree/main/scripts): Python scripts for data processing and interfacing with the hardware.
- [`/arduino/`](https://github.com/TharushaVJ/AI-Aim-Assist/tree/main/arduino): Arduino sketches for the Leonardo.
- [`/data/`](https://github.com/TharushaVJ/AI-Aim-Assist/tree/main/data): Datasets used for training the object detection model.

## How It Works

1. **Screen Capture**: The game screen is captured in real-time using a capture card .
2. **Enemy Detection**: The captured screen feed is processed by the TensorFlow model running on the Raspberry Pi, with the Coral Edge TPU USB Accelerator speeding up the inference.
3. **Data Processing**: The model outputs the coordinates of detected enemies, which are then processed to determine the necessary mouse movements.
4. **Mouse Control**: The Arduino Leonardo receives the processed data and adjusts the mouse position accordingly to aim at the detected enemies.

## Getting Started

### Prerequisites

- Raspberry Pi 4
- Coral Edge TPU USB Accelerator
- Arduino Leonardo
- Capture Card
- Python 3.11.4
- TensorFlow / TensorFlow Lite
- Arduino IDE

### Installation

1. **Clone this repository**:
    ```bash
    git clone https://github.com/TharushaVJ/AI-Aim-Assist.git
    cd AI-Aim-Assist
    ```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [TensorFlow](https://www.tensorflow.org/) for providing powerful tools to create machine learning models.
- [Coral](https://coral.ai/) for the TPU accelerator.
