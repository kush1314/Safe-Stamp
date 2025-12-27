# SafeStamp

SafeStamp is an open-source AI safety and education platform that embeds invisible, cryptographically verifiable watermarks into AI-generated images using Least Significant Bit (LSB) watermarking. Instead of guessing whether an image is real or fake, SafeStamp enables **100% verifiable provenance** by tying each image directly to its original prompt. The project is designed to educate users, demonstrate the limits of AI classifiers, and promote transparent, scalable solutions to AI misinformation.

---

## Inspiration

Have you ever looked at an image online and wondered: *“Was this real, or did AI generate it?”* You’re not alone.

A recent survey found that **79% of people in the U.S. believe misinformation is one of AI’s top dangers**. Most people have already encountered AI-generated images, headlines, or deepfakes without realizing it. This is becoming an educational crisis. In today’s world, it’s harder than ever to determine whether the content we see online is authentic or artificially generated.

We tested popular detection tools like OpenAI’s ChatGPT, Google’s Gemini, and Hive, and even built our own **AI Judge agent** in Windsurf to classify images as AI-generated or not. While helpful, none were 100% accurate. Our AI Judge reached about **80% accuracy**, proving that classifiers alone leave room for error and misinformation.

That’s where **SafeStamp** comes in.

SafeStamp uses **Least Significant Bit (LSB) watermarking** to embed an invisible cryptographic fingerprint directly into the pixels of AI-generated images. Each watermark is tied to the original prompt, stored securely, and fully verifiable. If an image is generated through SafeStamp, its origin can always be proven—without visually changing the image.

SafeStamp is built for **education, scalability, and transparency**. The platform teaches users how to think critically about AI-generated content, highlights real-world misinformation statistics, and demonstrates why watermarking is essential for AI safety. Because SafeStamp is **open-source**, anyone—students, teachers, or companies—can inspect the code, understand how watermarking works, and experiment with it themselves.

Unlike closed systems such as Google’s SynthID or Meta’s Stable Signature, SafeStamp is transparent and accessible. It is designed for classrooms, learning environments, and organizations that want a clear, trustworthy approach to AI image provenance.

---

## What It Does

SafeStamp allows users to generate AI images using **Hugging Face’s FLUX.1-schnell model**, with every image stamped using an invisible LSB watermark tied to the original prompt.

Users can upload images back into the system to verify authenticity, instantly mapping an image to the exact prompt used to create it. To reinforce learning, SafeStamp exposes the full watermarking process through open-source code and visual explanations.

The platform also presents key statistics—such as how often people fail to detect AI-generated images and why classifiers fall short—helping users understand the limitations of detection-based approaches. SafeStamp encourages critical thinking and demonstrates why watermarking is a scalable, reliable solution for AI safety.

---

## How We Built It

- **Backend:** Flask API with routes such as `/chat`, `/encode`, and `/verify`
- **Watermarking:** LSB embedding using a SHA-256 hash of `(prompt + secret key)`
- **Database:** SQLite for storing prompts and watermark records
- **Frontend:** HTML, CSS, and JavaScript (with an optional Gradio interface)
- **Judge Agent:** Windsurf-based AI agent to test classifier accuracy and expose detection gaps
- **Security:** Environment-based secrets and hashed prompt storage
- **IDE:** Windsurf

---

## Challenges We Faced

A major challenge was making watermarks invisible while keeping them reliably extractable across different images. We also worked within Hugging Face API limits, balancing stability and rate caps to keep the platform free and usable.

At the same time, we focused on building a simple, classroom-friendly interface that avoided unnecessary technical complexity. Competing with large, closed solutions pushed us to maintain transparency while still delivering a practical, scalable system.

---

## Accomplishments

- Built a **100% verifiable image provenance system** using LSB watermarking  
- Linked every generated image to its original prompt via a backend database  
- Designed an intuitive, educational interface for non-technical users  
- Delivered a fully **open-source** tool to combat AI misinformation  

---

## What We Learned

- AI classifiers alone are not reliable for determining authenticity  
- Watermarking provides the strongest guarantee for provenance  
- Visualization makes complex concepts like LSB understandable  
- Education and transparency are essential for public trust  
- And finally—coding can be fun :)

---

## What’s Next

- **Shared watermark registry** for public verification across AI platforms  
- **Education kits** including browser extensions, lesson plans, and demos  
- **Resilience research** to strengthen watermark survival under compression and edits  
- **Policy alignment** with global provenance standards such as **C2PA**
