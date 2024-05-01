# Visual Fact Checker
Description to add.

# Requirements
To run this project, you need an Anthropic API key, an OpenAI API key and python >= 3.8.

You can install the required Python packages by running the following command:

```
pip install -r requirements.txt
```

# Setup
Clone this repository to your local machine.
Create a .env file in the project directory and add your Anthropic API key in the following format:

```
ANTHROPIC_API_KEY=your_api_key_here
OPENAI_API_KEY=your_api_key_here
```

Replace your_api_key_here with your actual API keys.

# Usage
To play with the captioning method, just input an image in the visual_fact_checker_2d.ipynb notebook.
This notebook performs the following:
- Querying of Claude 3 Haiku and GPT-4V for image captioning.
- Querying of Haiku to generate a mixed caption using the two captions.
- Querying of Haiku to parse objects within caption.
- Use of Grounding Dino to verify the presence of said objects.
- Querying of Haiku to exploit GroundingDino results and generate a complete, verified caption.
- Querying of GPT4V to compare the original image captions to the verified captions.

# Notes
In the text image I choose, there are two things to note:
- Flipping GPT4 and Haiku descriptions has an impact on the mixed caption. GPT4's is better, but its captioning will be predominant if used as caption 1. On the opposite, Haiku hallucinates more, which leads to its error propagating if used as caption 1.
- On the last step, if Haiku is used as the evaluator, it decides its captioning is better, but it hallucinates regarding the image, as it sees two adults instead of one.

# Contributing
If you would like to contribute to this project, please follow these steps:
- Fork the repository.
- Create a new branch for your feature or bug fix.
- Make your changes and commit them with descriptive commit messages.
- Push your changes to your forked repository.
- Submit a pull request to the main repository, explaining your changes and their benefits.

# License
This project is licensed under the MIT License.

# Acknowledgments
- Claude-3 is developed by Anthropic.
- Gpt-4 is developed by OpenAI.
