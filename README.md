# my-portfolio.github.io
my portfolio on github
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive AI Prompt Builder</title>
    <style>
        body {
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            line-height: 1.6;
            max-width: 600px;
            margin: 40px auto;
            padding: 0 20px;
            color: #333;
        }
        h1 {
            color: #24292e;
            border-bottom: 1px solid #eaecef;
            padding-bottom: 10px;
        }
        label {
            display: block;
            font-weight: bold;
            margin-top: 20px;
            margin-bottom: 5px;
        }
        select, input, textarea {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
        }
        textarea {
            height: 100px;
            resize: vertical;
        }
        .output-container {
            margin-top: 30px;
            background-color: #f6f8fa;
            border: 1px solid #e1e4e8;
            border-radius: 6px;
            padding: 20px;
        }
        button {
            background-color: #2ea44f;
            color: white;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            font-weight: bold;
            border-radius: 6px;
            cursor: pointer;
            margin-top: 15px;
            width: 100%;
        }
        button:hover {
            background-color: #2c974b;
        }
        .copy-status {
            text-align: center;
            color: #2ea44f;
            font-weight: bold;
            margin-top: 10px;
            display: none;
        }
    </style>
</head>
<body>

    <h1>🤖 AI Prompt Builder</h1>
    <p>Select your options below to construct a structured AI prompt.</p>

    <label for="role">1. Act as a...</label>
    <select id="role" onchange="updatePrompt()">
        <option value="Expert Web Developer">Expert Web Developer</option>
        <option value="Creative Copywriter">Creative Copywriter</option>
        <option value="Data Analyst">Data Analyst</option>
        <option value="Career Coach">Career Coach</option>
    </select>

    <label for="task">2. What is the task?</label>
    <input type="text" id="task" value="explain how JavaScript event listeners work" oninput="updatePrompt()">

    <label for="tone">3. Desired Tone</label>
    <select id="tone" onchange="updatePrompt()">
        <option value="beginner-friendly and encouraging">Beginner-friendly & Encouraging</option>
        <option value="professional and concise">Professional & Concise</option>
        <option value="witty and engaging">Witty & Engaging</option>
    </select>

    <div class="output-container">
        <label for="finalPrompt">Generated Prompt:</label>
        <textarea id="finalPrompt" readonly></textarea>
        <button onclick="copyPrompt()">📋 Copy Prompt</button>
        <div id="copyStatus" class="copy-status">Copied to clipboard!</div>
    </div>

    <script>
        function updatePrompt() {
            const role = document.getElementById('role').value;
            const task = document.getElementById('task').value;
            const tone = document.getElementById('tone').value;
            
            const promptText = `Act as a ${role}. Your task is to ${task}. Please ensure the response is written in a ${tone} tone.`;
            
            document.getElementById('finalPrompt').value = promptText;
        }

        function copyPrompt() {
            const copyText = document.getElementById("finalPrompt");
            copyText.select();
            copyText.setSelectionRange(0, 99999); // For mobile devices
            navigator.clipboard.writeText(copyText.value);
            
            const status = document.getElementById("copyStatus");
            status.style.display = "block";
            setTimeout(() => {
                status.style.display = "none";
            }, 2000);
        }

        // Initialize the prompt on page load
        window.onload = updatePrompt;
    </script>

</body>
</html>
