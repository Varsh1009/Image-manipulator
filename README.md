Image Manipulator
Overview

This project is an image manipulation tool that follows the Model-View-Controller (MVC) architecture, enabling users to load, edit, and save images. It supports various image formats and provides functionalities such as filtering, brightening, flipping, and applying effects like blur, sepia, and sharpening.

Packages Overview

The project consists of three major packages in the src directory, each corresponding to a different component in the MVC structure:

model:

Contains the core logic for image manipulation.
Classes:
Color: Represents a pixel's red, green, and blue components.
Image: Stores and manipulates image pixels as a 2D array of Color objects.
ManipulatorModel: Interface defining core image operations like loading, saving, and manipulating images.
ImageManipulatorModel: Implementation of ManipulatorModel that includes all image operations (e.g., flipping, brightening, applying filters).
view:

Responsible for user interaction and displaying menus.
Classes:
ManipulatorView: Interface for displaying information to users and receiving input.
ImageManipulatorView: Implements the view, handling display and user prompts.
controller:

Controls the flow of data between the model and the view, processing user commands and delegating operations to the model.
Classes:
ImageEditorController: The central controller that processes commands and manages image manipulations.
ImageEditorMain: The entry point of the application that initializes the view, controller, and handles command-line inputs or script-based execution.
Running the Program

Running with Scripts

The program supports running a sequence of image manipulation commands from a script. To run the scripts located in the scripts folder, use the following commands:

run scripts/script1.txt
run scripts/script2.txt
This will execute all commands listed in each script file, process them, and save the resulting images as specified.

Running Commands Individually

You can also run individual commands as command-line inputs. Here are some examples:

Load an Image:

load /path/to/image.jpg imageName
Loads an image from the specified path and refers to it as imageName within the program.

Save an Image:

save /path/to/output.jpg imageName
Saves the image referred to as imageName to the specified file path.

Apply Red Component:

red-component imageName redImage
Extracts the red component of imageName and saves it as redImage. Similarly, you can use green-component, blue-component, value, luma, and intensity to extract other components.

Flip Image Horizontally:

horizontal-flip imageName flippedImage
Flips imageName horizontally and saves it as flippedImage.

Flip Image Vertically:

vertical-flip imageName flippedImage
Flips imageName vertically and saves it as flippedImage.

Brighten Image:

brighten 50 imageName brightenedImage
Brightens imageName by 50 and saves it as brightenedImage.

RGB Split:

rgb-split imageName redImage greenImage blueImage
Splits imageName into three images corresponding to its red, green, and blue components.

RGB Combine:

rgb-combine combinedImage redImage greenImage blueImage
Combines redImage, greenImage, and blueImage into a single image with the name combinedImage.

Blur Image:

blur imageName blurredImage
Blurs imageName and saves the result as blurredImage.

Sharpen Image:

sharpen imageName sharpenedImage
Sharpens imageName and saves the result as sharpenedImage.

Apply Sepia Tone:

sepia imageName sepiaImage
Applies a sepia tone to imageName and saves it as sepiaImage.

Test Cases

Test cases have been developed for both the model and controller components to ensure robust functionality and performance. These test cases validate the core image manipulation features, confirming that the implemented operations behave as expected under various conditions.

Model Tests

The test suite checks the functionality of the ImageManipulatorModel by comparing manipulated images on a pixel-by-pixel basis.

Component Tests (Red, Green, Blue, Value, Intensity, Luma): The expected image pixels were manually calculated based on the input image's original pixels. These tests compare each pixel of the resulting image against hardcoded values.
Blur, Sepia, Sharpen Tests: Instead of hardcoding the expected values, pre-existing images were used for comparison. The manipulated images' pixel data were verified by comparing them to these pre-processed reference images.
Each test validates the correctness of image manipulation by ensuring that the pixel values match the expected output.

Controller Tests

The controller tests validate the functionality of the ImageEditorController class. These tests ensure that image loading, saving, and manipulation features are correctly processed.

Key Features Tested:

Image Loading & Saving
Image Manipulation (Brightening, Flipping, Color Components)
Script Execution
Command Processing
Error Handling for invalid file paths and commands
Image Citation

duck.jpg, duck.ppm: The image used in this project (duck.jpg) is an original photograph taken by Shrivarshini Narayanan at Fenway Park. I am the owner of this image and authorize its use in this project.
Other images: manhattan-small.png, manhattan-small-sharper.png, manhattan-small-sepia.png, and manhattan-small-blur.png were provided as part of the starter code.
