# Image Editor

## Introduction

This assignment, titled "Image Editor" is a Java project that implements a simple image editing
application following the Model-View-Controller (MVC) architectural pattern. The project comprises
various components, each serving a specific role in the application. This README provides an
overview of the key components and their functionalities.

## Components

### 1. ImageEditor

The "ImageEditor" class serves as the entry point for the image editing application. It sets up the
environment for users to interact with the program through text-based commands which are
entered in the console or the commands are executed through a text file. Image processing and
control are handled by the respective classes, "ImageOperatorImpl" and "ImageControllerImpl".

### 2. ImageController

The "ImageController" is an interface that defines methods for sending and executing commands
related to image operations via text parsing. It throws exceptions for invalid commands and
input/output issues. The ImageController also gives the user the option to execute a text file
containing a list of commands by passing the file path as an argument to the "run" method.
The user can also execute the commands directly from the console by passing the command as an
argument to the "run" method.

### 3. ImageOperator

The "ImageOperator" interface represents an image operator. It is only main model interface that the
controller has access to. It provides a comprehensive set of methods for loading, saving,
processing, and applying filters to images. These methods handle exceptions related to file
operations and image processing. Additionally, it offers features such as adjusting brightness,
combining images, splitting images into color channels, and retrieving image details using the
"ImageDetails" data structure.

### 4. ImageLoader

The "ImageLoader" interface focuses on loading images as "ImageDetails" and saving "ImageDetails" to
specified paths. It handles exceptions related to file operations, ensuring smooth image loading and
saving processes.

### 5. ImageDetails

The "ImageDetails" class encapsulates the details of an image, including its width, height, maximum
value, and the red, blue, and green color channels as 2D float arrays. It follows the Builder design
pattern, allowing structured creation of "ImageDetails" instances with customizable attributes. This
class provides a robust approach to managing and accessing image details.

### 6. ImageFilter

The "ImageFilter" interface is responsible for applying custom kernels as filters to modify images
represented by "ImageDetails." It includes methods for applying matrix kernels and linear kernels to
process input images and returns the processed image as "ImageDetails".

### 7. ImageProcessor

The ImageProcessor interface provides essential methods for image manipulation, including
visualizing individual color channels (red, green, blue), combining grayscale images into a
color image, flipping images horizontally or vertically, adjusting image brightness or darkness, 
and dithering an image. Additionally, it offers a unique function to visualize different color
representations like luma, intensity, and value, enhancing the analysis and manipulation of image 
data.

### 8. ImageHistogram

The ImageHistogram interface enables creation and manipulation of image histograms.
It provides methods for generating histograms, applying color correction and levels adjust on the 
image. It also includes methods for split view of the color correct and levels adjusted image.

### 9. ImageCompressor

The ImageCompressor interface is designed for compressing images. It provides the
method for compression, allowing users to reduce image file size while
maintaining varying degrees of image quality. The interface includes the method
compressImageLossy which reduces quality but offers higher compression rates. This interface is
crucial for managing image storage efficiently.

### 10. ImageView

The ImageView interface is responsible for displaying the image and the filtered image. It also
displays the error message if the image is not found. It also refreshes the histogram and adds the
features to the controller.

### 11. MockImageOperator

The ImageMockOperator class is a mock class that implements the ImageOperator interface. It is used
for testing the Controller and the model.

### 12. MockImageView

The MockImageView class is a mock class that implements the ImageView interface. It is used for
testing the Controller and the view.

## How to run the program

1. Run the main program in the "ImageEditor" class.
2. Enter the command in the console.
3. If the command starts with "-file", enter the path of the text file along with the
   "-file" command containing the list of commands.
4. If any other valid command is entered, the program will execute the command and prompt for
   another command.
5. If an invalid command is entered, the program will prompt for another command.
6. To exit the program, enter "exit" as the command.

### Run program using JAR file

1. Execute the JAR file in the res folder on the terminal by
   typing the following command: java -jar ImageProcessor.jar
2. Enter the commands in the console.
3. Run the command "-file commands.txt" to run the commands in the text file

## Overall flow of the program

1. The user enters a command in the console.
2. The command is parsed and validated.
3. If the command is valid, the program executes the command.
4. If the command is invalid, the program prompts for another command.
5. The program continues to prompt for commands until the user enters "exit" as the command.
6. The program exits.
7. If the user enters the "-file" command, the program executes the commands in the text file.
8. If the command is valid, it is passed onto the ImageController.
9. The command goes to the executeCommand method in the ImageController where the appropriate method
   in the appropriate class is called based on the command and further processing takes place.


## Screenshots

- Sepia Preview Operation
  ![Sepia Preview](ImageEditorFeatures/sepia-preview.jpg)


- Color Correct Operation
  ![Color Correct](ImageEditorFeatures/color-correct.jpg)


- Greyscale Operation
  ![Greyscale](ImageEditorFeatures/greysclale-preview.jpg)


- Adjust Levels Operation
  ![Greyscale](ImageEditorFeatures/adjust-levels.jpg)


- Horizontal Flip, Vertical Flip
- ![Horizontal](ImageEditorFeatures/horizontal-flip.jpg)
  ![Vertical](ImageEditorFeatures/vertical-flip.jpg)


- Color Components
  ![Red](ImageEditorFeatures/red.jpg)
  ![Green](ImageEditorFeatures/green.jpg)
  ![Blue](ImageEditorFeatures/blue.jpg)


- Blur, Sharpen
  ![Blur](ImageEditorFeatures/blur.jpg)
  ![Sharpen](ImageEditorFeatures/sharpen.jpg)


- Compress
  ![Compress](ImageEditorFeatures/compress.jpg)


- Dither
  ![Dither](ImageEditorFeatures/dither.jpg)

