Image Feature Extraction with ResNet50
This project demonstrates how to extract deep features from a set of images using the ResNet50 model from TensorFlow. The extracted features are normalized and stored for downstream applications like image clustering, retrieval, or visual similarity detection.

📌 Overview
Feature Extraction: Utilizes the pre-trained ResNet50 model (trained on ImageNet) with the top classification layer removed and a GlobalMaxPooling2D layer added for feature vector extraction.

Batch Processing: Efficiently handles large datasets by processing images in batches — ideal for systems with limited memory.

Output Files: Each batch generates two .pkl files:

embeddings_batch_X.pkl: Numpy arrays of extracted features.

filenames_batch_X.pkl: Corresponding image filenames.

🧩 Dependencies
Make sure the following Python libraries are installed:

bash
Copy
Edit
pip install numpy tensorflow tqdm
📁 Dataset
Place all your images in a folder named images in the same directory as the script.

Example dataset (optional): Fashion Product Images Dataset on Kaggle

🚀 Usage Instructions
Step 1: Prepare Your Images
Create a folder named images in the project directory and place all images to be processed inside.

bash
Copy
Edit
project-directory/
│
├── Sample/
│   ├── image1.jpg
│   ├── image2.jpg
│   └── ...
└── feature_extraction.py
Step 2: Run the Script
You have two options to run the script depending on your system's memory capacity:

✅ Option A: Process All Batches at Once
If your system has enough resources:

Uncomment the full script logic.

Run the script:

bash
Copy
Edit
python feature_extraction.py
✅ Option B: Process One Batch at a Time
For systems with limited memory:

Split the dataset into batches (script does this automatically).

Uncomment only one batch section (e.g., Batch 1).

Run the script:

bash
Copy
Edit
python feature_extraction.py
Repeat for each batch.

💾 Output Files
Each batch generates the following:

embeddings_batch_X.pkl: Extracted features.

filenames_batch_X.pkl: Image filenames for each embedding.

Example for Batch 1:

Copy
Edit
embeddings_batch_1.pkl
filenames_batch_1.pkl
⚙️ Configuration
Batch Count: Default is 5; can be modified in the script.

Model: Uses ResNet50 from tensorflow.keras.applications without the top layer.

Pooling Layer: GlobalMaxPooling2D to flatten features.

🛠️ Troubleshooting
Memory Errors: Use smaller batches or process one batch at a time.

File Not Found: Ensure the images folder exists and is correctly named.

Missing Dependencies: Reinstall using the provided pip install command.

📄 License
This project is open-source and available for personal, educational, or academic use.

