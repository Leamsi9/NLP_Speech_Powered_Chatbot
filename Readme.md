This is a template for a speech/text-powered GUI for chatscript bots. There is an English version (Luke) and a Spanish version (Lucas) with demo bots included. It is coded in PHP, JavaScript and ChatScript, and uses the Web Speech API.

The Chatbots:  
The Luke Skywalker and Lucas Trotacielos bots have been created using the ChatScript language and engine. They are simple demo bots coded for a 5-10 minute conversation about free time. They can run on their own in the console as text only bots using the ChatScript engine. This repo adds a GUI whereby you can interact with the bots using either text, or your microphone to speak with them.

The chatbots are built on a much simplified version of the Harry bot template created by Bruce Wilcox and included in the ChatScript repo. 


The GUI:  
The GUI is a simple webpage with an image avatar. It has a text interface, and a microphone interface, using the Web Speech Api. I drew on the Alaric bot repo for inspiration on the speech functionality, and the ChatScript php template for the UI. In keeping with the Star Wars theme I have used CSS to replicate the iconic intro text from the movies, but separated the file so you can use your own styling.

Issues:  
This was intended as proof of concept demo rather than a full app. Accordingly a few limitations: 
1) Voicing questions:  When interacting using speech alone, the speech recognition API is not very good at recognising questions. Sentences beginning with "what" should work, but if you want to ask a different type of question it is better typed. The ChatScript compiler will pick up anything with a question mark at the end.

2) Chat log:  my Star Wars animation appends every new text to the line before. Beause the text is auto-scrolling, once it gets past view future chats are not visible. This can happen with large pauses. It does not affect the functionality at all, just the visibility.

3) Sound:  When the microphone is on, it picks up all speech. This means that if you are not using headphones, you have to pause the microphone button after you have voiced your answers, otherwise the bot will pick up its own voice responses as answers. If you have headphones you can just leave the microphone button active and chat, using the keyboard to text any questions not starting with "what"


Installation:  

Chatbots:  
The chatbots require the ChatScript repo installed (https://github.com/bwilcox-1234/ChatScript), and use the Harry configuration to run. The Luke/Lucas chatbot folders and accompannying files should be pasted into the RAWDATA folder of the ChatScript repo.

The GUI:  
The ui.php file is geared up to run locally. In order to do so you need to simulate a ChatScript server. You do this by simply running the LocalServer.bat file in the batch files folder of the ChatScript repo. It will by default use port 1024 and IP 0.0.0.0. You will need to configure the ui.php file with your own local IP address.

The Web Speech API:  
The current demo is configured for a Windows machine, and the Web Speech API uses the voices available to your computer. In the speech_chatbot.js file, on line 14, the voice to use is defined, by array index number, e.g.:
  u.voice = voices[6]; //English voice
You can change the number to access your preferred voice. If you are using OSx the voices will be different.

Comments and suggestions:  
Let me know any ideas and improvements by raising an issue on github, as I may use this as a basis for more serious applications. Also let me know if you use it for anything. It is good to know!