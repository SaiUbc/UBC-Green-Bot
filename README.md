# UBC CIC Gen AI and Sustainability Hackathon 2024

A key sustainability goal defined by the UN includes clean and affordable energy; industry, innovation, and infrastructure; responsible consumption and production; climate action; and sustainable cities and communities. Energy use is a major aspect of UBC operations, hosting over 60,000 students and 16,000 staff on more than 400 hectares. 

In this project we implemented retrieval augmented generation (RAG) using various AWS services to create a chatbot with a visualization feature to allow users to ask questions about energy usage at UBC. This will allow policy makers and teams such as Campus and Community Planning to make informed, data based decisions on improving energy use and making critical infrastructure changes.

We parsed the raw CSV file to a text file with rows of the building name, date, and energy use. We uploaded this file to Amazon S3, and connected this to a Amazon Bedrock Knowledge Base for RAG. In the Lambda function, we configured the Knowledge Base to prompt Claude 3 Sonnet with an engineered prompt returning a written answer and raw data to display on a chart. The front end is built with Streamlit, and graphs are drawn with Matplotlib. 

UBC's energy usage data is available here: https://energy.ubc.ca/projects/skyspark/

![alt text](./pics/arch_diagram.png "Architecture diagram")

# Demo

![gif demo](./pics/UBC_Green_Bot_DEMO.gif)

# Check this out!

![Development Journey](/docs/development_journey.md): I talk about my motivation for this project and my development journey.
![Prompt Examples](./docs/prompt_examples.md): Check the capabilities and use case examples of this project.

# File Structure
```bash
├── data/
│   └── data.txt (actual data fed into AWS S3 BUCKET)
│   └── test_data.txt
│   └── DESDES_No_Units.csv
│   └── DESDESPlants.csv
│   └── EnergyUsage_No_Units.csv
│   └── EnergyUsage.csv
├── docs/
│   └── development_journey.md 
│   └── prompt_examples.md 
├── lamda/
│   └── lamda_function.py (added lambda function)
├── pics/
│   └── DEMO gif (added gif for demo)
│   └── /.png (contains all the demp pics)
├── src/
│   └── app.py (updated to use .env)
├── .gitignore (added gitignore)
├── .env (added to .gitignore)
├── LICENSE (Initial commit)
├── README.md 
├── requirements.txt (added requirements with all dependencies)
```

# How to use

To install the required dependencies, run the following command in your terminal:

```shell
pip install -r requirements.txt
```

Once the installation is complete, you can start the Streamlit app by running the following command:

```shell
python3 -m streamlit run app.py
```

Make sure you are in the correct directory where the `streamlit_app.py` file is located.

# Contributors and Acknowledgement

I'd like to extend my gratitude to the UBC Cloud Innovation Center for organizing this hackathon. It was a valuable learning experience, particularly in exploring the latest technologies, including the practical applications of GenAI and playing around with AWS to get to know it better. 

I also want to thank my teammates for their invaluable contributions to this project:
- ![@jasonioio](https://github.com/jasonioio)
- ![@griffw00](https://github.com/griffw00)

