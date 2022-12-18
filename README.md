# Convert real-world photos between Monet painting  
Team members: Weimeng Chen, Ivy Cheng
### Description:
We generate a photo-realistic image representing the same content without leveraging paired training data with CycleGANs approach: Convert real-world photos to similar Monet paintings (style) and Convert Monet paintings to real-world photos(style). We want to increase the realism of generated images in image-to-image translation and show what reality the artist was observing or imagining while drawing.
### Repository and Code Structure:
- `gan-monet-photo.ipynb` utilizes a CycleGAN architecture to add Monet-style to photos.
- `evaluation_img` folder contains evaluation of the generator models including how good is the generator cycle. We get a photo to generate a Monet picture from it, then use the generated picture to generate the original photo.
- Data: https://www.kaggle.com/competitions/gan-getting-started/data
<img width="1128" alt="image" src="https://user-images.githubusercontent.com/75918977/208309523-2a2618a2-f6a8-4e36-a0b1-3110bfebb7be.png">

### Example commands to execute the code:
- Please run the notebook on Kaggle since the data is imported from Kaggle
- TPU execution is recommended
- Please follow the instruction in the `gan-monet-photo.ipynb`

### Results:
- Monet generator
![image](https://user-images.githubusercontent.com/75918977/208309951-8802fa57-251c-48b4-bf96-16df2fc4b4aa.png)

  - Monet generator Loss:
  - ![image](https://user-images.githubusercontent.com/75918977/208310140-66ea6d30-9d34-4464-8ede-2214c5d376db.png)

- Photo generator:
![image](https://user-images.githubusercontent.com/75918977/208310163-1db316aa-cb34-43cb-9ba8-1311e9847b26.png)

  - Photo generator Loss:
  - ![image](https://user-images.githubusercontent.com/75918977/208310190-5cab52ab-248b-407c-8baf-e3da5112b5b8.png)
  
### Conclusion:
- The binary cross entropy losses for both Monet generator and Photo generator are decreasing. 
- The losses for both discriminators do not have significant changes
- We cannot see a good progress on both Monet generator and Photo generator within 30 epochs. Losses of generators are still too high
- Future Work:
  - The generator models need to be trained more (more epochs)
  - Consider to try better model structure of generator 
    - Number of hidden layers
    - Parameter of convolutional layer (filter size, padding, stride)
    - Combination of upsample and downsample
    - (such as Encoder-Transformer-Decoder)

### Reference:
- https://proceedings.neurips.cc/paper/2014/file/5ca3e9b122f61f8f06494c97b1afccf3-Paper.pdf
- https://www.kaggle.com/competitions/gan-getting-started
- https://junyanz.github.io/CycleGAN/
- https://openaccess.thecvf.com/content_ECCVW_2018/papers/11130/Tomei_What_was_Monet_seeing_while_painting_Translating_artworks_to_photo-realistic_ECCVW_2018_paper.pdf
