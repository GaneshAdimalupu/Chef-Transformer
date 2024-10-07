
# **Be My Chef AI - Recipe Generation from Food Images**

![Be My Chef AI Logo](static/images/logo.png) <!-- Replace with the actual path to your logo image -->

Are you curious about recreating delicious dishes from just a picture? **Be My Chef AI** is here to help! This project leverages advanced AI models to generate detailed recipes based on food images. By analyzing a picture of a dish, the system predicts the ingredients and provides step-by-step cooking instructions to recreate it.

## **Demo**

[![Demo Video](static/images/demo.png)](http://localhost:8501) <!-- Replace with a link to your demo video or live app -->

Upload an image, and watch as the AI generates a complete recipe for you!

## **Features**

- **Image-Based Ingredient Prediction**: Upload a food image, and the AI predicts the ingredients present.
- **Recipe Generation**: Generates a detailed recipe with a title, ingredients list, and cooking instructions.
- **Multiple Chef Models**: Choose between different chef personas for varied recipe styles.
- **User-Friendly Interface**: Easy-to-use interface built with Streamlit.

## **Model Details**

The application uses a combination of Convolutional Neural Networks (CNNs) and Transformer models:

- **CNN Encoder**: Processes the input food image to extract visual features.
- **Ingredient Decoder**: Predicts the ingredients present in the dish.
- **Transformer Decoder**: Generates the cooking instructions based on the predicted ingredients and image features.

## **Setup Instructions**

### **1. Prerequisites**

#### a. **Install Conda (if not installed)**

Download and install Miniconda from the [official website](https://docs.conda.io/en/latest/miniconda.html) suitable for your operating system.

#### b. **Download Model Files**

You need to download three essential files for the model to function:

1. **Model Weights**: [Download `modelbest.ckpt`](https://dl.fbaipublicfiles.com/inversecooking/modelbest.ckpt)
2. **Ingredients Vocabulary**: [Download `ingr_vocab.pkl`](https://dl.fbaipublicfiles.com/inversecooking/ingr_vocab.pkl)
3. **Instruction Vocabulary**: [Download `instr_vocab.pkl`](https://dl.fbaipublicfiles.com/inversecooking/instr_vocab.pkl)

Place these files in the `Foodimg2Ing/data/` directory within your project folder.

### **2. Installation**

#### a. **Clone the Repository**

```bash
git clone https://github.com/GaneshAdimalupu/Recipe-Generation-from-Food-Image.git
cd Recipe-Generation-from-Food-Image
```

#### b. **Create and Activate Conda Environment**

```bash
conda create -n ganesh python=3.8
conda activate ganesh
```

#### c. **Install Dependencies**

```bash
pip install -r requirements.txt
```

### **3. Running the Application**

Start the Streamlit app by running:

```bash
streamlit run app.py
```

After running this command, you will see output similar to:

```
You can now view your Streamlit app in your browser.

  Local URL: http://localhost:8501
  Network URL: http://192.168.X.XXX:8501
```

Open the `Local URL` in your web browser to interact with the app.

## **Using the App**

1. **Upload a Food Image**: Click on "Choose a food image" and select an image (`jpg`, `jpeg`, or `png`).
2. **View Uploaded Image**: The app will display the image you've uploaded.
3. **Ingredient Prediction**: The app processes the image and predicts the ingredients.
4. **Select Chef Model**: Choose between "Chef Scheherazade" or "Chef Giovanni" for different recipe styles.
5. **Generate Recipe**: Click on "Get Recipe!" to generate the recipe.
6. **View Recipe**: The app will display the recipe title, ingredients list, and cooking instructions.

## **Project Structure**

```
Recipe-Generation-from-Food-Image/
├── app.py                        # Main Streamlit app file
├── data/
│   ├── ingr_vocab.pkl            # Ingredients vocabulary
│   ├── instr_vocab.pkl           # Instructions vocabulary
│   └── modelbest.ckpt            # Trained model weights
├── Foodimg2Ing/
│   ├── __init__.py
│   ├── args.py                   # Argument parser
│   ├── model.py                  # Model architecture
│   ├── output.py                 # Prediction functions
│   └── routes.py                 # API routes (if using Flask)
├── modules/
│   ├── encoder.py                # CNN encoder modules
│   ├── multihead_attention.py    # Attention mechanisms
│   └── transformer_decoder.py    # Transformer decoder modules
├── static/
│   ├── css/
│   │   └── style.css             # Stylesheets
│   └── images/                   # Static images for the app
├── utils/
│   ├── api.py                    # API utilities
│   ├── draw.py                   # Image drawing utilities
│   ├── output_utils.py           # Output processing utilities
│   └── ...                       # Other utility scripts
├── requirements.txt              # Python dependencies
└── README.md                     # This file
```

## **Dependencies**

Ensure all dependencies are installed by running:

```bash
pip install -r requirements.txt
```

Key dependencies include:

- **Streamlit**: For building the web interface.
- **PyTorch**: Deep learning framework for model implementation.
- **Transformers**: For utilizing Transformer models.
- **Pillow**: Image processing.
- **Torchvision**: For image transformations and pre-trained models.

## **Troubleshooting**

### **Common Errors and Solutions**

- **ModuleNotFoundError**: If you encounter errors about missing modules, ensure that all dependencies are installed and that your Python environment is correctly set up.

- **FileNotFoundError for Model Files**: Verify that `modelbest.ckpt`, `ingr_vocab.pkl`, and `instr_vocab.pkl` are placed in the correct directory (`Foodimg2Ing/data/`).

- **AttributeError in Streamlit**: If you receive errors like `'NoneType' object has no attribute 'format'`, ensure that the image generation function returns a valid image URL or handle cases where the image may be `None`.

- **CUDA Errors**: If you encounter CUDA-related warnings and you don't have a GPU or prefer to run on CPU, you can disable CUDA by setting the environment variable before running the app:

  ```bash
  export CUDA_VISIBLE_DEVICES=-1
  ```

- **Port Already in Use**: If Streamlit indicates that the default port `8501` is in use, specify a different port:

  ```bash
  streamlit run app.py --server.port 8502
  ```

## **Contributing**

Contributions are welcome! Please open an issue or submit a pull request on GitHub if you have suggestions or improvements.

## **License**

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## **Acknowledgments**

- The model is inspired by the work from [Inverse Cooking: Recipe Generation from Food Images](https://arxiv.org/abs/1812.06164).
- Thanks to the developers of Streamlit for providing an easy way to build web apps.

## **Contact**

For any inquiries or support, please contact:

- **Ganesh Adimalupu**
- **Email**: [your_email@example.com](mailto:your_email@example.com)
- **GitHub**: [GaneshAdimalupu](https://github.com/GaneshAdimalupu)
