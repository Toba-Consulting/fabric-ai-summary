# How to Set Up and Use Fabric: An AI-Powered Command-Line Tool

## Prerequisites:

- A computer running Linux, macOS, or Windows with WSL (Windows Subsystem for Linux)
- Basic familiarity with command-line interfaces
- API keys for OpenAI, Anthropic (optional), and YouTube (optional)

## Installation:

1. Update your system:
    
    ```
    sudo apt update
    sudo apt upgrade
    ```
    
2. Clone the Fabric repository:
    
    ```
    git clone <https://github.com/danielmiessler/fabric.git>
    ```
    
3. Install PIP X:
    - For Linux/WSL:
        
        ```
        sudo apt install pipx
        ```
        
    - For macOS:
        
        ```
        brew install pipx
        ```
        
4. Install Fabric:
    
    ```
    cd fabric
    pipx install .
    ```
    
5. Ensure Fabric is in your PATH:
    
    ```
    pipx ensurepath
    ```
    
6. Refresh your terminal:
    - For Linux/WSL:
        
        ```
        source ~/.bashrc
        ```
        
    - For macOS:
        
        ```
        source ~/.zshrc
        ```
        
7. Set up Fabric:
    
    ```
    fabric --setup
    
    ```
    
    - Enter your API keys when prompted

## Basic Usage:

1. List available patterns:
    
    ```
    fabric --list
    ```
    
2. Use a pattern:
    
    ```
    echo "Your text here" | fabric -s -p pattern_name
    
    ```
    
3. Extract wisdom from a YouTube video:
    
    ```
    yt-transcript [VIDEO_URL] | fabric -s -p extract_wisdom
    ```
    
4. Use a specific AI model:
    
    ```
    fabric --model model_name -s -p pattern_name
    ```
    
5. Change the default model:
    
    ```
    fabric --change-default-model model_name
    ```
    

## Advanced Features:

1. Stitching patterns:
    
    ```
    echo "Your text" | fabric -p summarize | fabric -s -p write_essay
    ```
    
2. Create custom patterns:
    - Create a directory: `~/.config/fabric/my_patterns`
    - Create a new pattern directory: `mkdir ~/.config/fabric/my_patterns/new_pattern`
    - Create a system prompt file: `nano ~/.config/fabric/my_patterns/new_pattern/system.md`
    - Copy custom patterns to Fabric: `cp -r ~/.config/fabric/my_patterns/* ~/.config/fabric/patterns/`
3. Use context:
    - Edit the context file: `nano ~/.config/fabric/context`
4. Save output to Obsidian:
    - Set up Obsidian path: Edit `~/.config/fabric/env`
    - Use the save command: `fabric -p pattern_name | fabric save note_name`

## Tips and Tricks:

1. Use the `improve_prompt` pattern to refine your custom patterns.
2. Experiment with different patterns for various tasks like summarizing articles, analyzing claims, or rating content.
3. Utilize local AI models with Fabric for offline use or to avoid API costs.
4. Regularly update Fabric and its patterns: `fabric --update`
5. Combine Fabric with other command-line tools for powerful text processing workflows.

## Troubleshooting:

1. If Fabric commands are not recognized, ensure your PATH is correctly set up.
2. For API-related issues, double-check your API keys in the `~/.config/fabric/env` file.
3. If a pattern isn't working as expected, try updating Fabric and its patterns, or refine the pattern using the `improve_prompt` feature.

Remember, Fabric is designed to augment your capabilities, not replace your critical thinking. Use it as a tool to enhance your productivity and learning, while still engaging deeply with important content when necessary.