1. Data Acquisition & Preprocessing

Source: Utilized the dog-vs-cat dataset from Kaggle, accessed via kagglehub.

Data Balancing: Implemented a custom loader to ensure a 500:500 balanced split between classes, preventing the model from becoming biased toward one animal.

Standardization: Images were converted to Grayscale and resized to 64×64 pixels to maintain uniform input dimensions for the feature extractor.

2. Feature Extraction: The HOG Descriptor

Instead of using raw pixels (which are sensitive to lighting and background), you used Histogram of Oriented Gradients (HOG).

Why HOG? It captures the structural distribution (gradients) of the image.

Geometric Shapes: It identifies the "edge" patterns of a cat's pointy ears versus a dog’s floppy ears, allowing the model to ignore background noise like grass or furniture.

3. The Model: Support Vector Machine (SVM)

RBF Kernel: You chose a Radial Basis Function (RBF) kernel, which allows the model to create a non-linear "decision boundary" in a high-dimensional space.

Optimization: Through Grid Search, you tuned the C parameter (Penalty) to 10 and set Gamma to scale, ensuring the model generalizes well to new, unseen images.

4. Handling Modern Formats

Compatibility: Integrated Pillow and imagecodecs to solve real-world data issues, allowing the model to read modern high-compression formats like .avif and .jxl.

5. Final Performance Results

Precision: The model achieved an exceptional 98.95% precision for Dogs and 98.31% precision for Cats.

Success Story: The transition from raw pixels (82%) to HOG features (98%+) demonstrated how Feature Engineering is often more important than the algorithm itself in Computer Vision.


OUTPUT: https://drive.google.com/drive/folders/1fnXru_PRzj2zKWX7zIyv3OII-7GWaEap
