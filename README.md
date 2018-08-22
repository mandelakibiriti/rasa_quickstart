# Tutorial to create Rasa Core bot on local command line
1. Install rasa core package

    `pip install rasa_core`

2. Create stories.md and domain.yml files that contain the intents, actions and templates. Example of these files can be found at this [link](https://rasa.com/docs/core/quickstart/)

3. Train bot with the script below. This will create a folder called models with a subfolder called 'dialogue'

    `python -m rasa_core.train -d domain.yml -s stories.md -o models/dialogue`

4. Run the bot using the script below. To talk to the bot send a message such as `/greet` and the bot shall respond with the action outlined in the template

    `python -m rasa_core.run -d models/dialogue`

5. Install rasa_nlu package

    `pip install rasa_nlu`

6. Create nlu.md and nlu_config.yml files as found at this [link](https://rasa.com/docs/core/quickstart/)

7. Train NLU model with the script below and a subfolder under models called 'current/nlu' will be created

    `python -m rasa_nlu.train -c nlu_config.yml --data nlu.md -o models --fixed_model_name nlu --project current --verbose`

8. Run bot for using the script below

    `python -m rasa_core.run -d models/dialogue -u models/current/nlu`
