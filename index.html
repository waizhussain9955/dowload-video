<?php
if ($_SERVER["REQUEST_METHOD"] === "POST") {
    header("Content-Type: application/json");
    
    // ✅ Check if yt-dlp is installed
    $yt_dlp_installed = shell_exec("yt-dlp --version");
    if (!$yt_dlp_installed) {
        echo json_encode(["message" => "Error: yt-dlp is not installed. Install it using 'pip install yt-dlp'."]);
        exit;
    }

    // ✅ Read JSON Request
    $data = json_decode(file_get_contents("php://input"), true);
    $video_url = $data["url"] ?? '';

    if (!$video_url) {
        echo json_encode(["message" => "URL is required"]);
        exit;
    }

    // ✅ System Downloads Folder
    $downloads_folder = getenv("HOME") . "/Downloads"; // Mac/Linux
    if (PHP_OS_FAMILY === 'Windows') {
        $downloads_folder = getenv("USERPROFILE") . "\\Downloads"; // Windows
    }

    // ✅ Download Command
    $command = escapeshellcmd("yt-dlp -f best -o \"$downloads_folder/%(title)s.%(ext)s\" $video_url 2>&1");

    // ✅ Execute Command
    $output = shell_exec($command);

    if (strpos($output, "ERROR") !== false) {
        echo json_encode(["message" => "Error downloading video", "details" => $output]);
    } else {
        echo json_encode(["message" => "Download completed! Check your Downloads folder."]);
    }
    exit;
}
?>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>YouTube Video Downloader (PHP + yt-dlp)</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin-top: 50px;
        }
        input, button {
            padding: 10px;
            margin: 10px;
            font-size: 16px;
        }
    </style>
</head>
<body>
    <h2>YouTube Video Downloader (PHP + yt-dlp)</h2>
    <input type="text" id="video_url" placeholder="Enter YouTube URL">
    <button onclick="downloadVideo()">Download</button>
    <p id="status"></p>

    <script>
        function downloadVideo() {
            const url = document.getElementById("video_url").value;
            document.getElementById("status").innerText = "Downloading...";

            fetch('', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ url: url })
            })
            .then(response => response.json())
            .then(data => {
                document.getElementById("status").innerText = data.message;
            })
            .catch(error => {
                document.getElementById("status").innerText = "Error downloading video";
            });
        }
    </script>
</body>
</html>
