# 🧠 Mindvoice : AI-Narrated Interactive Mindmaps

A beautiful, interactive mindmap visualization tool that brings your ideas to life with AI-powered content generation and podcast-style narration. Built with p5.js and modern web technologies, featuring a stunning glassmorphism UI design.

## ✨ Features

-   **AI-Powered Content Generation**: Use the built-in generator to create a complete mindmap on any topic by leveraging Perplexity AI.
-   **Podcast-Style Narration**: Experience your mindmap as a narrated podcast with alternating, natural-sounding voices that guide you through each concept.
-   **Multi-Language Support**: Generate mindmaps and listen to narration in multiple languages, including English, Hindi, and Bengali.
-   **Interactive Visualization**: Smoothly pan, zoom, and explore complex mindmaps with intuitive controls.
-   **Dynamic UI**: A sleek, collapsible side panel with a modern glassmorphism design for all controls.
-   **Expandable Nodes**: Click to expand and collapse branches to focus on specific areas of the mindmap.
-   **Smart Info Display**: A dedicated info box at the bottom displays the title and technical notes of the currently selected or narrated node.
-   **Full JSON Control**: Easily load data by pasting, uploading a file, or generating with AI. Download your mindmap as a JSON file to save your work.
-   **Robust JSON Parsing**: The tool automatically finds and fixes JSON data pasted from AI chats, even with extra text or code fences.
-   **Responsive Design**: The interface and visualization adapt seamlessly to different screen sizes.

## 🚀 Getting Started

It's a single, self-contained HTML file. No installation is needed!

1.  Download the `index.html` file and open it in a modern web browser (like Chrome, Firefox, or Edge).
2.  **To Generate Content:**
    -   Open the side panel using the `☰` button.
    -   Enter a topic (e.g., "Quantum Computing").
    -   Provide a brief description for context (e.g., "Explain for a beginner").
    -   Select your desired language.
    -   Click "Generate with Perplexity AI". A new tab will open with the generated JSON.
    -   Copy the entire response and use the "Paste & Load" button in the app.
3.  **To Use Your Own Data:**
    -   Paste your JSON into the textarea and click "Load Mindmap".
    -   Alternatively, click "Upload" to load a local `.json` file.
4.  Click the **🔊** button to start the podcast-style narration.

## 🎮 Controls

| Action              | Control                  |
| ------------------- | ------------------------ |
| Pan Canvas          | Click and drag background|
| Zoom                | Mouse wheel scroll       |
| Expand/Collapse Node| Click on a node          |
| Start/Stop Narration| Click the **🔊** button  |
| Toggle Control Panel| Click the `☰` button     |

## 📋 JSON Structure

The application uses a specific hierarchical JSON structure. The `script` field is crucial for the podcast narration.

```json
{
  "id": "unique_snake_case_id",
  "title": "Concise Node Title",
  "notes": "A brief, one-sentence technical summary of the concept.",
  "script": "An engaging, conversational script for narration (2-3 sentences).",
  "children": [ /* other nodes with the same structure */ ]
}
```

### Field Descriptions:

-   `id` (required): A unique identifier for the node (e.g., `quantum_entanglement`).
-   `title` (required): The display text for the node.
-   `notes` (optional): A short, technical summary shown in the info box.
-   `script` (optional but recommended): The text that will be read aloud during the narration. This should be conversational and easy to understand. If omitted, the `title` and `notes` will be used as a fallback.
-   `children` (optional): An array of child nodes to create the hierarchy.

## 📖 Example JSON

Here's a complete example you can copy and paste to see the tool in action:

```json
{
  "id": "root",
  "title": "Programming Fundamentals",
  "notes": "Core concepts for every programmer.",
  "script": "Welcome! Let's explore the fundamentals of programming, the building blocks of all software.",
  "children": [
    {
      "id": "data_structures",
      "title": "Data Structures",
      "notes": "Methods for organizing data.",
      "script": "First up, Data Structures. Think of these as special containers, each designed to store and organize data in an efficient way.",
      "children": [
        {
          "id": "arrays",
          "title": "Arrays",
          "notes": "A simple list of items.",
          "script": "The simplest is an Array. It's like a numbered list of boxes, perfect for quickly accessing items if you know their position."
        },
        {
          "id": "linked_lists",
          "title": "Linked Lists",
          "notes": "A flexible chain of items.",
          "script": "Then we have Linked Lists. Instead of a fixed list, each item points to the next, making it super flexible to add or remove elements."
        }
      ]
    },
    {
      "id": "algorithms",
      "title": "Algorithms",
      "notes": "Step-by-step procedures for calculations.",
      "script": "Next, let's talk about Algorithms. These are like recipes: a set of rules to follow to solve a specific problem.",
      "children": [
        {
          "id": "sorting",
          "title": "Sorting",
          "notes": "Arranging data in order.",
          "script": "A common task is Sorting. Algorithms like 'Bubble Sort' or 'Quick Sort' help us arrange data from smallest to largest, or alphabetically."
        }
      ]
    }
  ]
}
```

## 🤖 AI Prompt for Generating JSON

Use this powerful prompt with any AI assistant (ChatGPT, Claude, Perplexity, etc.) to generate compatible mindmap JSON for any topic.

````
Create a comprehensive, educational mindmap as a JSON object on the topic: "[YOUR TOPIC HERE]".
Context: [YOUR CONTEXT HERE, e.g., "Explain for a 10th-grade class"]
Language Requirement: The entire output, including all titles, notes, and scripts, MUST be in [YOUR LANGUAGE HERE, e.g., English, Hindi].

JSON Requirements:
1.  **Strict JSON Format:** Adhere to this exact structure for every node.
    {
      "id": "unique_snake_case_id",
      "title": "Concise Node Title",
      "notes": "A brief, one-sentence technical summary of the concept.",
      "script": "An engaging, conversational script for a podcast-style narration. Explain the concept clearly in 2-3 sentences as if talking to a student. Make it easy to understand.",
      "children": [ /* other nodes */ ]
    }
2.  **Content Guidelines:**
    -   The root node must be the main topic "[YOUR TOPIC HERE]".
    -   Create 3-5 main branches from the root.
    -   Go 3-4 levels deep to provide substantial detail.
    -   IDs must be unique and use snake_case.
    -   **Crucially, the "script" field must be well-written for audio narration in [YOUR LANGUAGE HERE].**
3.  **Output:**
    -   Provide **ONLY** the raw JSON object without any explanatory text or markdown code fences.

Start the JSON now:
````

## 🛠 Technical Details

-   **Core Library**: [p5.js](https://p5js.org/) for interactive graphics and animation.
-   **Audio Engine**: Native browser Web Speech API (`SpeechSynthesis`) for text-to-speech.
-   **Dependencies**: None! It's a single, dependency-free HTML file that even works offline once loaded.
-   **Browser Support**: Works best on modern browsers that support the Web Speech API (Chrome, Edge, Firefox, Safari). Voice availability may vary by browser and OS.
