# 🧠 Interactive Mindmap with AI Narration

A beautiful, interactive mindmap visualization tool with AI-powered podcast-style narration. Built with p5.js and modern web technologies, featuring a stunning glassmorphism UI design.

## ✨ Features

- **Interactive Visualization**: Pan, zoom, and explore hierarchical data structures
- **AI Narration**: Podcast-style narration with alternating voices and dynamic highlighting
- **Glassmorphism UI**: Modern, translucent interface with blur effects
- **Expandable Nodes**: Click to expand/collapse branches dynamically
- **Smart Tooltips**: Hover over nodes to see detailed information
- **JSON Input**: Easy data loading through JSON structure
- **Responsive Design**: Works on desktop and mobile devices
- **Keyboard Shortcuts**: Space for narration, R for reset

## 🚀 Getting Started

1. Download the HTML file
2. Open it in a modern web browser
3. Paste your JSON data into the left panel
4. Click "Load Mindmap" to visualize
5. Use the 🔊 button to start AI narration
6. Use the ⟳ button to reset the view

## 🎮 Controls

| Action | Control |
|--------|---------|
| Pan | Click and drag |
| Zoom | Mouse wheel |
| Focus on node | Double-click node |
| Expand/Collapse | Click node |
| Start/Stop narration | 🔊 button or Spacebar |
| Reset view | ⟳ button or R key |
| Toggle JSON panel | ← button |

## 📋 JSON Structure

The application uses a hierarchical JSON structure where each node can have children:

```json
{
  "id": "unique_identifier",
  "title": "Node Title",
  "notes": "Detailed description for tooltips and narration",
  "children": [
    {
      "id": "child_id",
      "title": "Child Node",
      "notes": "Child description",
      "children": []
    }
  ]
}
```

### Required Fields:
- `id`: Unique identifier for the node
- `title`: Display text for the node

### Optional Fields:
- `notes`: Additional information (shows in tooltips and narration)
- `children`: Array of child nodes (creates hierarchy)

## 📖 Example JSON

Here's a complete example you can copy and paste:

```json
{
  "id": "root", 
  "title": "Web Development",
  "notes": "Modern web development technologies and practices",
  "children": [
    {
      "id": "frontend",
      "title": "Frontend Development",
      "notes": "Client-side technologies for user interfaces",
      "children": [
        {
          "id": "html",
          "title": "HTML5",
          "notes": "Semantic markup and document structure"
        },
        {
          "id": "css",
          "title": "CSS3",
          "notes": "Styling, animations, and responsive design"
        },
        {
          "id": "javascript",
          "title": "JavaScript",
          "notes": "Dynamic behavior and interactivity",
          "children": [
            {
              "id": "frameworks",
              "title": "Frameworks",
              "notes": "Popular JavaScript frameworks",
              "children": [
                {
                  "id": "react",
                  "title": "React",
                  "notes": "Component-based library for building UIs"
                },
                {
                  "id": "vue",
                  "title": "Vue.js",
                  "notes": "Progressive framework for building UIs"
                }
              ]
            }
          ]
        }
      ]
    },
    {
      "id": "backend",
      "title": "Backend Development",
      "notes": "Server-side logic and data management",
      "children": [
        {
          "id": "nodejs",
          "title": "Node.js",
          "notes": "JavaScript runtime for server development"
        },
        {
          "id": "databases",
          "title": "Databases",
          "notes": "Data storage and management systems",
          "children": [
            {
              "id": "sql",
              "title": "SQL Databases",
              "notes": "Relational databases like PostgreSQL, MySQL"
            },
            {
              "id": "nosql",
              "title": "NoSQL Databases",
              "notes": "Document and key-value stores like MongoDB, Redis"
            }
          ]
        }
      ]
    },
    {
      "id": "tools",
      "title": "Development Tools",
      "notes": "Tools and practices for efficient development",
      "children": [
        {
          "id": "version_control",
          "title": "Version Control",
          "notes": "Git and GitHub for code management"
        },
        {
          "id": "deployment",
          "title": "Deployment",
          "notes": "Hosting and CI/CD pipelines"
        }
      ]
    }
  ]
}
```

## 🤖 AI Prompt for Generating JSON

Use this prompt with any AI assistant (ChatGPT, Claude, etc.) to generate mindmap JSON for any topic:

```
Create a detailed mindmap JSON structure for the topic: [YOUR TOPIC HERE]

Requirements:
1. Use exactly this JSON format:
{
  "id": "unique_id",
  "title": "Node Title", 
  "notes": "Detailed explanation of this concept",
  "children": []
}

2. Structure Guidelines:
   - Root node should be the main topic
   - Create 3-5 main branches (children of root)
   - Each main branch should have 2-4 sub-branches
   - Go 3-4 levels deep maximum
   - Use snake_case for all id fields
   - Make titles concise but descriptive
   - Include informative notes for each node (1-2 sentences)
   - Ensure each id is unique across the entire structure

3. Content Guidelines:
   - Cover the most important aspects of the topic
   - Include both theoretical concepts and practical applications
   - Make it educational and comprehensive
   - Notes should be suitable for audio narration

Topic: [YOUR TOPIC HERE]

Please generate the complete JSON structure following these exact requirements.
```

### Example Usage:
```
Topic: Machine Learning
```
or
```
Topic: Cooking Fundamentals
```
or
```
Topic: Personal Finance
```

## 🛠 Technical Details

- **Built with**: p5.js, HTML5, CSS3, JavaScript
- **Browser Support**: Modern browsers with Speech Synthesis API
- **No Dependencies**: Single HTML file, works offline
- **Responsive**: Adapts to different screen sizes

## 🎨 Customization

The glassmorphism theme can be customized by modifying CSS variables:
```css
:root {
  --bg-color: #0a0a10;
  --text-color: #f0f0f0;
  --glass-bg: rgba(25, 25, 40, 0.3);
  --glass-border: rgba(255, 255, 255, 0.15);
}
```

## 🔊 Audio Features

- **Multi-voice narration**: Alternates between different voices
- **Smart highlighting**: Visual sync with audio
- **Auto-expansion**: Automatically opens nodes during narration
- **Pitch variation**: Different pitch for different speakers
- **Pause/resume**: Full control over narration playback

## 📱 Mobile Support

- Touch gestures for pan and zoom
- Responsive button layout
- Collapsible JSON panel
- Optimized for smaller screens

## 🤝 Contributing

Feel free to fork, modify, and improve this project. Some ideas for contributions:

- Additional themes and color schemes
- Export functionality (PNG, SVG, PDF)
- Import from other formats (XML, YAML)
- Enhanced animation effects
- Custom voice selection
- Search and filter functionality

## 📄 License

This project is open source and available under the MIT License.

***

**Made with ❤️ for interactive learning and beautiful data visualization**
