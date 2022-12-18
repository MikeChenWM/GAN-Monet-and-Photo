# Convert real-world photos between Monet painting  
Team members: Weimeng Chen, Ivy Cheng
### Description:
We generate a photo-realistic image representing the same content without leveraging paired training data with CycleGANs approach: Convert real-world photos to similar Monet paintings (style) and Convert Monet paintings to real-world photos(style). We want to increase the realism of generated images in image-to-image translation and show what reality the artist was observing or imagining while drawing.
### Repository and Code Structure:
- `gan-monet-photo.ipynb` utilizes a CycleGAN architecture to add Monet-style to photos.
- `evaluation img` folder contains evaluation of the generator models including how good is the generator cycle. We get a photo to generate a Monet picture from it, then use the generated picture to generate the original photo.
- Data: https://www.kaggle.com/competitions/gan-getting-started/data
<img width="1128" alt="image" src="https://user-images.githubusercontent.com/75918977/208309523-2a2618a2-f6a8-4e36-a0b1-3110bfebb7be.png">
### Example commands to execute the code:
Please follow the instruction in the `gan-monet-photo.ipynb`
### Results:





Demo planned:

References: https://openaccess.thecvf.com/content_ECCVW_2018/papers/11130/Tomei_What_was_Monet_seeing_while_painting_Translating_artworks_to_photo-realistic_ECCVW_2018_paper.pdf
https://arxiv.org/abs/1907.10830
https://arxiv.org/abs/1703.10593

Document: https://docs.google.com/document/d/16gC1irmrS2DD7wefUKq9jrQwYhZBUslUr9Kn1-gZDk8/edit?usp=sharing
