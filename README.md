# Tutorial to create Rasa Core bot on local command line
1. Install rasa core package
`pip install rasa_core`
2. Create stories.md and domain.yml files that contain the intents, actions and templates. Example of these files can be found at this [link](https://rasa.com/docs/core/quickstart/)
3. Train bot with the script below. This will create a folder called models
`python -m rasa_core.train -d domain.yml -s stories.md -o models/dialogue`
4. Run the bot using the script below. To talk to the bot send a message such as `/greet` and the bot shall respond with the action outlined in the template
`python -m rasa_core.run -d models/dialogue`