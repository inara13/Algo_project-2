# Algo_project-2

##Q-1 How to install tinytroupe packages?
##To install tinytroupe need to follow below steps:

run below code
pip install tinytroupe

After installation you can check the tinytroupe:
pip show tinytroupe


##Q-2 What is Turing Test? In today's world with Large Language Models (LLMs), what is the definition of Turing Test?

Alan Turing developed the Turing Test in 1950 to determine whether a machine can replicate human intellect sufficiently that a human judge would be unable to tell it apart in a text-based exchange.

The test's applicability in the age of Large Language Models (LLMs) like GPT-4 is up for dispute. Although LLMs are capable of producing replies that are remarkably human-like, they are devoid of true comprehension, reasoning, and self-awareness; instead, they make text predictions based on patterns rather than real cognition.

Traditional Turing Tests are less relevant in the context of modern AI evaluation, which emphasizes long-term reasoning, adaptability, and real-world problem-solving.  The Winograd Schema Challenge is one of the more recent options that attempts to evaluate deeper intelligence as opposed to only conversational mimicking.

##Q-3 Create a simulation of your own topic and show me the transcript. This implies define at least two personas of your own choice with conflict built in and observe their conversation. You can simply copy/paste the conversation in a .md file. Please comment on the transcript whether you think the Turing Test is passed.


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

>>> lisa_ds = create_lisa_the_data_scientist()
>>> lisa_ds.listen_and_act("Tell me about your life.")
USER --> Lisa Carter: [CONVERSATION] 
          > Tell me about your life.
Lisa Carter acts: [THINK] 
                 > I need to share about my life, including my background, education, and current
                 > job. I should also mention my interests and hobbies to give a well-rounded view.
Lisa Carter acts: [TALK] 
                 > Sure! I grew up in Vancouver, Canada, in a tech-savvy family. My parents were
                 > software engineers, which inspired my interest in technology from a young age. I
                 > pursued a Master's in Data Science at the University of Toronto, where I focused
                 > on improving search relevance using context-aware models. Now, I work as a Data
                 > Scientist at Microsoft in the M365 Search team, analyzing user behavior to
                 > enhance search results. In my free time, I enjoy cooking, playing the piano, and
                 > watching movies, especially comedies and thrillers.
Lisa Carter acts: [DONE] 

>>> from tinytroupe.agent import TinyPerson
>>> inara = TinyPerson("Inara")
>>> inara.define("age", 24)
>>> inara.define("nationality", "Indian")
>>> inara.define("occupation", "She is a intern in PACE  university.")
>>> inara.listen_and_act("Tell me about yourself.")
USER --> Inara: [CONVERSATION] 
          > Tell me about yourself.
Inara acts: [THINK] 
           > I need to introduce myself. I should mention my name, age, nationality, and what I do.
Inara acts: [TALK] 
           > My name is Inara, I'm 24 years old, and I'm from India. Currently, I'm an intern at
           > PACE University. I'm excited to learn and grow in my field.
Inara acts: [DONE] 

>>> from tinytroupe.agent import TinyPerson
>>> jonny = TinyPerson("Jonny")
>>> jonny.define("age", 18)
>>> jonny.define("nationality", "American")
>>> jonny.define("occupation", "He is a student in a university.")
>>> from tinytroupe.environment import TinyWorld
>>> world = TinyWorld("Classroom", [inara, jonny])
>>> world.make_everyone_accessible()
>>> inara.listen("I want to extend my work.")
USER --> Inara: [CONVERSATION] 
          > I want to extend my work.
TinyPerson(name='Inara')
>>> world.run(3)
──────────────────────────────────────────────────────────────── Classroom step 1 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > I need to understand what they mean by extending their work. Should I ask for more
           > details?
Inara acts: [TALK] 
           > Could you please elaborate on what you mean by extending your work? I'm interested to
           > hear more about your ideas.
Inara acts: [DONE] 

Inara --> Jonny: [CONVERSATION] 
           > My name is Inara, I'm 24 years old, and I'm from India. Currently, I'm an intern at
           > PACE University. I'm excited to learn and grow in my field.
Inara --> Jonny: [CONVERSATION] 
           > Could you please elaborate on what you mean by extending your work? I'm interested to
           > hear more about your ideas.
Jonny acts: [TALK] 
           > Hi Inara! It's great to meet you. I'm Jonny, a university student as well. I'm curious
           > about your internship at PACE University. What specific field are you working in?
Jonny acts: [DONE] 

Jonny --> Inara: [CONVERSATION] 
           > Hi Inara! It's great to meet you. I'm Jonny, a university student as well. I'm curious
           > about your internship at PACE University. What specific field are you working in?
──────────────────────────────────────────────────────────────── Classroom step 2 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > I should share more about my internship and the specific field I'm working in. This is
           > a good opportunity to connect with Jonny.
Inara acts: [TALK] 
           > Hi Jonny! It's nice to meet you too. I'm currently interning in the field of education,
           > focusing on curriculum development and student engagement strategies. It's been a great
           > learning experience so far!
Inara acts: [DONE] 

Inara --> Jonny: [CONVERSATION] 
           > Hi Jonny! It's nice to meet you too. I'm currently interning in the field of education,
           > focusing on curriculum development and student engagement strategies. It's been a great
           > learning experience so far!
Jonny acts: [TALK] 
           > That sounds really interesting! Curriculum development is such an important area in
           > education. What specific strategies have you been working on for student engagement?
Jonny acts: [DONE] 

Jonny --> Inara: [CONVERSATION] 
           > That sounds really interesting! Curriculum development is such an important area in
           > education. What specific strategies have you been working on for student engagement?
──────────────────────────────────────────────────────────────── Classroom step 3 of 3 ────────────────────────────────────────────────────────────────
Inara acts: [THINK] 
           > I need to think about the specific strategies I've been working on for student
           > engagement. I should mention a few examples to give Jonny a clearer picture.
Inara acts: [TALK] 
           > I've been focusing on interactive learning strategies, such as group discussions and
           > project-based learning. These methods encourage students to collaborate and engage more
           > actively with the material. I've also been exploring the use of technology to enhance
           > learning experiences, like incorporating educational apps and online resources.
Inara acts: [DONE] 

Inara --> Jonny: [CONVERSATION] 
           > I've been focusing on interactive learning strategies, such as group discussions and
           > project-based learning. These methods encourage students to collaborate and engage more
           > actively with the material. I've also been exploring the use of technology to enhance
           > learning experiences, like incorporating educational apps and online resources.
Jonny acts: [TALK] 
           > Those interactive learning strategies sound fantastic! I think group discussions can
           > really help students express their ideas and learn from each other. How has the
           > response been from the students so far?
Jonny acts: [DONE] 

Jonny --> Inara: [CONVERSATION] 
           > Those interactive learning strategies sound fantastic! I think group discussions can
           > really help students express their ideas and learn from each other. How has the
           > response been from the students so far?

