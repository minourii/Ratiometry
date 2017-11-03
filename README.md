# Ratiometry
This is a plugin for ImageJ

    This plugin calculates the ratio between two images (single frames or stacks),
    as used in QuicGSH experiments, for example. The code -- heavily annotated to help
    beginners like myself explore the world of ImageJ -- is largely based on Ratio Plus
    and Image Calculator Plus by Dr. Paulo J. Magalhaes.
    (https://imagej.nih.gov/ij/plugins/ratio-plus.html)

    The plugin requires two images of the same width and height,
    and of the same type (8-, 16-, or 32-bit); the images must be:
        i) two single images;
       ii) two stacks with the same number of frames; or
      iii) a stack as a first image and a single frame as a second - in this case,
           the single frame will be applied throughtout the complete stack.

    The resulting image (in 32-bit) is calculated as follows:

         intensity = (R - Rmin) / (Rmax - R) * Kd
         R = intA/intB

    where intA, intB and intensity are the intensities of the first, second and ratio 
    images, respectively; Rmin and Rmax are constants entered by the user for the first 
    and second images, respectively; Kd is also a constant entered vy user.

    If a pixel value becomes negative after background subtraction, it is set to zero
    before ratio calculation.

    In addition, the plugin can accept clipping values for either of the images:
    if the pixel intensity (after background subtraction) is lower than the clipping value
    for that image, it is set to zero before ratio calculation; the clipping values for either
    image are set by the user.

    NB: if two corresponding pixels in the first and second images are zero, their ratio
    is set to 1 (one); i.e., "zero by zero" division equals one.

	History  Nov. 3. 2017  modified by Itsushi Minoura (GORYO Cheical Inc.)
