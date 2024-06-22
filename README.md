# IMC-2024
This is the solution we provided for the [_"Image Matching Challenge 2024 - Hexathlon"_](https://www.kaggle.com/competitions/image-matching-challenge-2024) Kaggle competition, where we won a **silver medal** (ranked **28/929**).

## Algorithm Descriptions:
1. **Retrieval**: Retrieval for various 3D scene image datasets, using pretrained model weights of efficientnet-b6&b7 from ImageNet to extract image data features. The selection is based on cosine distance, ranking the top n images in each scene dataset by similarity.
2. **Image Feature Keypoint Extraction and Matching**:
  - For the retrieved image library, use kornia’s corner feature detector CornerGFTT to extract relevant feature point locations. The AdaLAM algorithm is applied to calculate matches for all matching points, saving successful match pairs.
  - For the retrieved image library, use SuperPoint to extract relevant feature point locations. The SuperGlue algorithm is applied to calculate matches for all matching points, saving successful match pairs.
3. **Spatial Position Estimation**: Combine the successful match pairs from both processes of the image library, removing duplicates, and input into pycolmap to compute the final 3D spatial relationships (position and pose estimation).


