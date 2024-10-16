Create a new markdown file and edit the file with the browser interface. Alternatively, you can clone it, then commit changes, and push them (more about this in two weeks).
Add a to do list with things you have heard about today and would like to learn throughout the semester. You can update this list during the semester by checking things you have learned.
Add a table that documents the markdown syntax, which you can use as your personal cheat sheet throughout the semester.
Add a quote (about data science or sth. more general) that inspires you.
Add verbatim code. With a code snippet that is already familiar to you. Alternatively, write Python code that prints "Hello World!".
Add three other markdown-formatted contents. Also insert headings with appropriate levels.

# 1st Assignment

In this assignment there will be found the following:

1. **Data Modeling Module ToDo list** 
2. **markdown cheat sheet**
3. **my favorite quote(s)**
4. **.py code that converts audio files**
5. **project idea after DIS Bachelor**
6. **Rhythmus im Blut project**
7. **my desired internship semester**

## 1. Data Modeling Module ToDo list
  I already scraped some website for work with Beautifulsoup, although I did not unstand the code fully, because I used mainly ChatGPT. Therefore I want to:
  - learn how to write my own code to scrape the web
  - learn how to use GitHub

## 2. markdown cheat sheet
  |  | simple text options |  |
  | --- | --- | --- |
  | *what* | *how to* | *example* |
  | strong | \*\*text\*\* | **text** |
  | cursive | \*text\* | *text* |
  | escape | \\ | \*text\* |
  
  |  | *tables* |
  | --- | --- |
  | create row | \|  \| |
  | delimiter row | \| --- \| |

## 3. my favorite quote(s)
> # Miles Davis
> If you understood everything I say, you’d be me!

> # C. G. Jung
> To ask the right question is already half the solution of a problem.

## 4. **.py code that converts audio files**
  I actually used this code today (16.10.2024) to convert audio files to the .aiff format. I used ChatGPT though...
~~~
import os
import subprocess
def convert_to_aiff(input_file, output_file):
    try:
        ffmpeg_command = [
            'ffmpeg',
            '-i', input_file,
            '-map_metadata', '0',
            '-c:a', 'pcm_s16be',
            '-movflags', 'use_metadata_tags',
            output_file
        ]
        subprocess.run(ffmpeg_command, check=True)
        print(f"Erfolgreich konvertiert: {output_file}")
    except subprocess.CalledProcessError as e:
        print(f"Fehler bei der Konvertierung: {e}")
def convert_folder(input_folder, output_folder):
    for root, dirs, files in os.walk(input_folder):
        for file in files:
            # Überspringe .mp3 und .wav Dateien
            if not file.lower().endswith(('.mp3', '.wav')):
                if file.lower().endswith(('.flac', '.ogg', '.aac', '.m4a', '.wma')):  # Füge hier weitere Formate hinzu, falls nötig
                    input_file = os.path.join(root, file)
                    relative_path = os.path.relpath(root, input_folder)
                    target_folder = os.path.join(output_folder, relative_path)
                    os.makedirs(target_folder, exist_ok=True)
                    output_file = os.path.join(target_folder, os.path.splitext(file)[0] + '.aiff')
                    convert_to_aiff(input_file, output_file)
if __name__ == "__main__":
    input_folder = "C:/Users/merli/Music/_Auflegen"
    output_folder = "C:/Users/merli/Music/_AuflegenAIFF"
    convert_folder(input_folder, output_folder)
~~~

## 5. **project idea after DIS Bachelor**
  When I started the Bachelor my idea was to create an software or and database that supports recordsellers (music records) with API interfaces for wholesales and discogs .e.g.. 

## 6. **Rhythmus im Blut project**
  
## 7. **my desired internship semester**
  


