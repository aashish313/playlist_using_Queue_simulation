# Queue Simulation – Audio Playlist Player 🎵

This project is a **queue data structure simulation** implemented as a **beautiful browser-based audio player**.  
Users can upload audio files from their device, which are then stored in a **queue** and played in order with options to move to the **next**, **previous**, and **loop through the queue**. :contentReference[oaicite:0]{index=0}  

It is ideal as a **Data Structures / DAA mini-project** to demonstrate practical use of queues.

---

## ✨ Features

- Upload multiple audio files from your device.
- Songs are stored in a **queue** (FIFO-style playlist).
- **Play / Pause / Next / Previous** controls.
- **Loop Queue** option (on/off).
- Highlights the **currently playing** song in the playlist.
- Click any song in the queue to directly play it.
- Clean, modern **glassmorphism UI** with subtle animation.

---

## 🧠 Data Structure Logic (Queue Simulation)

Core logic is implemented using an `AudioQueue` class:

- `items[]` – stores the uploaded audio files in order.
- `currentIndex` – keeps track of which element in the queue is currently playing.
- `enqueue(x)` – inserts a new song at the **end** of the queue.
- `current()` – returns the **current** song object.
- `next(loop)` – moves to the next song:
  - If not at the end → `currentIndex++`
  - If at the end and `loop === true` → wraps back to `0`
- `prev(loop)` – moves to the previous song:
  - If not at the beginning → `currentIndex--`
  - If at the beginning and `loop === true` → wraps to `items.length - 1`

The HTML5 `<audio>` object is used to actually play the file corresponding to `queue.current()`.  
When a track ends (`audio.onended`), `queue.next()` is called automatically to simulate continuous queue playback.

---

## 🛠️ Technologies Used

- **HTML5** – Structure of the page.
- **CSS3** – Styling and animated glassmorphism UI.
- **Vanilla JavaScript** – Queue implementation and player logic.
- **HTML5 Audio API** – Playing audio via `new Audio()` and `URL.createObjectURL`.


## 📁 Project Structure

```text
.
├── index.html   # Contains HTML, CSS, and JavaScript (all in one file)
