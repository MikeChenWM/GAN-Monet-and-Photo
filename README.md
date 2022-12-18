# Convert real-world photos between Monet painting  
### Team members: Weimeng Chen, Ivy Cheng
- Goal/Objective: 
generate a photo-realistic image representing the same content without leveraging paired training data
	- Convert real-world photos to similar Monet paintings (style)
	- Convert Monet paintings to real-world photos(style)
- Challenges: 
Cannot use the ordinary metric to evaluate the performance. Evaluation of the performance would be difficult
…
- Approach/Techniques: CycleGANs
- Data: https://www.kaggle.com/competitions/gan-getting-started/data
- Implementation details: 
	- Input Image Size: 256 × 256 pixels. 
Set the channel to 3. Scale the images to a [-1, 1]. Return the image from the TFRecord.
Build the generator:
use a UNET architecture for CycleGAN. 
The downsample: reduces the 2D dimensions, the width and height, of the image by the stride. The stride is the length of the step the filter takes. Since the stride is 2, the filter is applied to every other pixel, hence reducing the weight and height by 2.
use instance normalization instead of batch normalization. Use the layer from TensorFlow Add-ons.
Build Discriminator
discriminator outputs a smaller 2D image
higher pixel values indicating a real classification and lower values indicating a fake classification.
Build the Cycle-GAN model
subclass a tf.keras.Model to run fit() later to train our model. 
the model transforms a photo to a Monet painting and then back to a photo. The difference between the original photo and the twice-transformed photo is the cycle-consistency loss. 
Batch size: 16, Learning Rate: 0.00002, Epochs: 30
Define loss functions
compares real images to a matrix of 1s and fake images to a matrix of 0s. The perfect discriminator will output all 1s for real images and all 0s for fake images. The discriminator loss outputs the average of the real and generated loss

Framework: Pytorch


Demo planned:

References: https://openaccess.thecvf.com/content_ECCVW_2018/papers/11130/Tomei_What_was_Monet_seeing_while_painting_Translating_artworks_to_photo-realistic_ECCVW_2018_paper.pdf
https://arxiv.org/abs/1907.10830
https://arxiv.org/abs/1703.10593

Document: https://docs.google.com/document/d/16gC1irmrS2DD7wefUKq9jrQwYhZBUslUr9Kn1-gZDk8/edit?usp=sharing
