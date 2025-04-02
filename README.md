##Q-1 How to install tinytroupe packages?
To Install Turing packages need to follow steps given below:

Open your terminal or command prompt.
Run the following command to install the tinytroupe package:

pip install tinytroupe

After installation, you can check that tinytroupe was installed successfully by running:

pip show tinytroupe

##Q-2 What is Turing Test? In today's world with Large Language Models (LLMs), what is the definition of Turing Test?

In a text-based interaction, Alan Turing's 1950 Turing Test determines whether a machine can accurately mimic human intelligence to the point where a human judge cannot tell it apart.

The test's applicability is up for question in the age of Large Language Models (LLMs) like GPT-4. LLMs can produce replies that are remarkably human-like, but they are not truly capable of thinking, reasoning, or self-awareness; rather, they make text predictions based on patterns rather than real cognition.

The relevance of classic Turing tests has diminished as modern AI evaluation places more emphasis on long-term reasoning, flexibility, and real-world problem-solving. More recent options, such as the Winograd Schema Challenge, seek to evaluate deeper intelligence as opposed to only linguistic mimicking.

##Q-3 Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a .md file. Please comment on the transcript whether you think the Turing Test is passed.

=================================
Current TinyTroupe configuration 
=================================
[OpenAI]
api_type = openai
azure_api_version = 2023-05-15
model = gpt-4o-mini
max_tokens = 4000
temperature = 1.2
freq_penalty = 0.0
presence_penalty = 0.0
timeout = 60
max_attempts = 5
waiting_time = 1
exponential_backoff_factor = 5
embedding_model = text-embedding-3-small
cache_api_calls = False
cache_file_name = openai_api_cache.pickle
max_content_display_length = 1024

[Simulation]
rai_harmful_content_prevention = True
rai_copyright_infringement_prevention = True

[Logging]
loglevel = ERROR

>>> lisa_ds = create_lisa_the_data_scientist() # instantiate a Lisa from the example builder
>>> lisa_ds.listen_and_act("Tell me about your life.")
USER --> Lisa Carter: [CONVERSATION] 
          > Tell me about your life.
Lisa Carter acts: [THINK] 
                 > Someone is asking me to tell them about my life. I should share my background,
                 > education, work, and interests in a concise manner.
Lisa Carter acts: [TALK] 
                 > Sure! I grew up in Vancouver, Canada, in a tech-savvy family. I pursued a
                 > Master's in Data Science at the University of Toronto, where I focused on
                 > improving search relevance using context-aware models. Now, I work as a Data
                 > Scientist at Microsoft in the M365 Search team, analyzing user behavior to
                 > enhance search results. I love learning about AI and machine learning, and in my
                 > free time, I enjoy cooking, playing the piano, and watching movies.
Lisa Carter acts: [DONE] 

>>> from tinytroupe.agent import TinyPerson
>>> inara = TinyPerson("Inara")
>>> inara.define("age", 24)  # Adjust the age as per your requirement
>>> 
>>> inara.define("nationality", "indian")
>>> inara.define("occupation", "she is a professor in a university.")
>>> 
>>> inara.listen_and_act("Tell me about yourself.")
USER --> Inara: [CONVERSATION] 
          > Tell me about yourself.
Inara acts: [THINK] 
           > I need to introduce myself and share some information about my background and
           > profession.
Inara acts: [TALK] 
           > My name is Inara, and I'm 24 years old. I'm from India and currently work as a
           > professor at a university. I enjoy teaching and sharing knowledge with my students. I
           > also have a passion for learning new things and exploring different cultures.
Inara acts: [DONE] 

>>> from tinytroupe.agent import TinyPerson
>>> john = TinyPerson("John")
>>> john.define("age", 22)  # Adjust the age as per your requirement
>>> 
>>> john.define("nationality", "American")
>>> john.define("occupation", "He is a student in a university.")
>>> from tinytroupe.environment import TinyWorld
>>> world = TinyWorld("Classroom", [inara, john])
>>> world.make_everyone_accessible()
>>> inara.listen("I want to extend my homework.")
USER --> Inara: [CONVERSATION] 
          > I want to extend my homework.
TinyPerson(name='Inara')
>>> world.run(3) # trigger the conversation with 3 rounds back-and-forth
──────────────────────────────────────────────────────────────── Classroom step 1 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > I need to respond to the request about extending homework. I should ask for more
           > details about why they need the extension and how much time they require.
Inara acts: [TALK] 
           > Can you tell me why you need an extension for your homework? How much extra time do you
           > think you will need?
Inara acts: [DONE] 

Inara --> John: [CONVERSATION] 
           > My name is Inara, and I'm 24 years old. I'm from India and currently work as a
           > professor at a university. I enjoy teaching and sharing knowledge with my students. I
           > also have a passion for learning new things and exploring different cultures.
Inara --> John: [CONVERSATION] 
           > Can you tell me why you need an extension for your homework? How much extra time do you
           > think you will need?
John acts: [THINK] 
          > Inara is asking about my homework extension. I need to explain my situation clearly and
          > specify how much extra time I need.
John acts: [TALK] 
          > I need an extension for my homework because I've been dealing with some unexpected
          > personal issues that have made it difficult for me to focus. I think I would need an
          > extra week to complete it properly.
John acts: [DONE] 

John --> Inara: [CONVERSATION] 
          > I need an extension for my homework because I've been dealing with some unexpected
          > personal issues that have made it difficult for me to focus. I think I would need an
          > extra week to complete it properly.
──────────────────────────────────────────────────────────────── Classroom step 2 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > I understand that John is going through a tough time and needs an extension. It's
           > important to be supportive while also ensuring he can complete his homework properly.
Inara acts: [TALK] 
           > Thank you for sharing that with me, John. I understand that personal issues can be
           > really challenging. I can grant you the extra week to complete your homework. Just make
           > sure to reach out if you need any further assistance during this time.
Inara acts: [DONE] 

Inara --> John: [CONVERSATION] 
           > Thank you for sharing that with me, John. I understand that personal issues can be
           > really challenging. I can grant you the extra week to complete your homework. Just make
           > sure to reach out if you need any further assistance during this time.
John acts: [THINK] 
          > Inara was understanding and granted me the extension. I should express my gratitude and
          > let her know I appreciate her support.
John acts: [TALK] 
          > Thank you so much, Inara! I really appreciate your understanding and support. I'll make
          > sure to reach out if I need any help during this time.
John acts: [DONE] 

John --> Inara: [CONVERSATION] 
          > Thank you so much, Inara! I really appreciate your understanding and support. I'll make
          > sure to reach out if I need any help during this time.
──────────────────────────────────────────────────────────────── Classroom step 3 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > John seems really grateful for the extension, and it's nice to see that he appreciates
           > my support. I should encourage him to take care of himself during this time.
Inara acts: [TALK] 
           > You're very welcome, John! I'm glad I could help. Remember, it's important to take care
           > of yourself during this time. If you need anything else, don't hesitate to ask.
Inara acts: [DONE] 

Inara --> John: [CONVERSATION] 
           > You're very welcome, John! I'm glad I could help. Remember, it's important to take care
           > of yourself during this time. If you need anything else, don't hesitate to ask.
John acts: [THINK] 
          > Inara is very supportive and emphasizes the importance of self-care. I should
          > acknowledge her advice and express my appreciation for her concern.
John acts: [TALK] 
          > Thank you, Inara! I really appreciate your concern and support. I'll definitely take
          > care of myself and reach out if I need anything else.
John acts: [DONE] 

John --> Inara: [CONVERSATION] 
          > Thank you, Inara! I really appreciate your concern and support. I'll definitely take
          > care of myself and reach out if I need anything else.
