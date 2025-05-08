# Voice Cloning for Urdu Song Generation

## Project Description

This project aims to develop a voice cloning model capable of generating Urdu songs in the style of a target artist, given new lyrics. The model is trained on a dataset of the artist's songs and their corresponding lyrics.

## Installation

1.  **Clone the repository:**

    ```bash
    git clone <repository_url>
    cd <repository_name>
    ```

2.  **Install the required dependencies:**
    * It is recommended to use a virtual environment.
        ```bash
        python -m venv venv
        source venv/bin/activate  # On Linux/macOS
        venv\Scripts\activate  # On Windows
        ```
    * Install the dependencies using pip.  It is assumed that you have `requirements.txt`. If not, follow the dependencies section to install the necessary packages.
        ```bash
        pip install -r requirements.txt
        ```

## Dependencies

The project relies on several Python libraries.  Here's a list of the core dependencies:

* torch (for deep learning)
* torchaudio (for audio processing)
* transformers (for model components)
* librosa (for audio feature extraction)
* soundfile (for reading/writing audio files)
* Other common packages: numpy, tqdm, etc. (These should be in the `requirements.txt` file)
