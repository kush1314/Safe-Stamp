Inspiration

Have you ever looked at an image online and wondered: “Was this real, or did AI generate it?” You’re not alone.
A recent survey found that 79% of people in the U.S. believe misinformation is one of AI’s top dangers. And most of us have already come across AI-generated images, headlines, or deepfakes without even realizing it. This is an educational crisis. In today’s world, it’s becoming harder than ever to determine if the content we see online is authentic or artificially generated.
We tested popular detection tools like OpenAI’s ChatGPT, Google’s Gemini, and Hive, and even built our own AI Judge agent in Windsurf to classify images as AI-generated or not. While useful, none were 100% accurate. Our AI Judge reached about 80% accuracy, but no classifier can perfectly guess reality, leaving room for error and misinformation.
That’s where SafeStamp comes in. We use Least Significant Bit (LSB) watermarking to embed an invisible cryptographic fingerprint directly into the pixels of AI-generated images. Each watermark is tied to the original prompt, stored securely, and 100% verifiable. This means if an image is made through our system, it can always be proven! The image is also visually unchanged!
SafeStamp is built for education, scalability, and transparency. On our platform, we educate users on what is AI-generated vs what is not! Additionally, we provide key statistics in the market today while showing them the importance of watermarking and AI Safety. Additionally, because SafeStamp is open-source, anyone—students, teachers, or even companies—can look at our code, understand how watermarking works, and try it for themselves!
This makes SafeStamp different from corporate tools like Google’s SynthID or Meta’s Stable Signature. Those systems are closed and hidden. Ours is open, simple to understand, and made for learning. For classrooms, it’s a way to teach students how to question and verify content. For companies, it’s proof that watermarking can scale and be used as a trusted way to track AI-generated content.

What it does

SafeStamp allows users to create AI images with Hugging Face’s FLUX.1-schnell model, and every image is stamped with an invisible LSB watermark tied to the original prompt. They can then upload images back into the system to verify authenticity, instantly mapping them to the exact prompt used. To make the learning real, SafeStamp is open-source and our algorithm for watermarking is accessible and easy to learn! Additionally, SafeStamp displays key statistics  (like how many people struggle to detect fakes or how classifiers fail at accuracy). in understanding AI Safety at the user's discretion. SafeStamp educates users to think critically about what they see online and shows why open-source watermarking is a powerful, scalable solution for AI safety.

How we built it

-Flask Backend for routes like /chat, /encode, /verify
-Watermarking with LSB: SHA-256 hash of (prompt + secret key) embedded invisibly into pixel values
-SQLite Database to store watermarks and prompts


Frontend UI: HTML/CSS/JS chat interface; optional Gradio app
-Judge Agent: built in Windsurf to test classifier accuracy and show detection gaps
-Security: .env secrets + hashed prompt storage
-IDE: Windsurf

Challenges we ran into

One of our biggest challenges was making watermarks invisible yet reliably extractable across different images. We also had to work within Hugging Face’s API limits—balancing token stability and rate caps to keep the platform free. At the same time, we focused on building a simple, classroom-friendly interface that stripped away complexity for non-technical users. In a space where big players like Google (SynthID) and Meta (Stable Signature) are pushing closed solutions, our challenge was to deliver an open-source alternative that stayed transparent, accessible, and educational.

Accomplishments that we're proud of

We are proud of building a 100% verifiable provenance system using LSB watermarking, paired with a simple, easy-to-use UI. We also integrated a database backend system that ties every image back to its original prompt. We are proud of creating a tool that is open-source and educational to fight against AI misinformation.

What we learned

-Classifiers alone (ChatGPT, Gemini, Hive, Windsurf Judge) aren’t reliable
-Watermarking is the most reliable solution for provenance
-Visualization makes abstract concepts like LSB understandable
-Education + openness are the keys to building public trust
-Finally, coding can be fun :)

What's next for our project

Shared watermark registry: AI companies embed watermarks in every image so the public can verify provenance
Education kits: browser extensions, lesson plans, and demos for classrooms worldwide
Resilience research: strengthening watermark survival under compression, crops, and edits
Policy alignment: working with global provenance initiatives like C2PA
