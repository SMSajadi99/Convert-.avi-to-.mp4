# Convert .avi to .mp4

## Step 1:
```python
pip install moviepy
```
## Step 2:
```python
from moviepy.editor import VideoFileClip

def avi_to_mp4(input_file, output_file):
    try:
        # Load the AVI file
        clip = VideoFileClip(input_file)

        # Set the output file format to mp4 and save the video
        clip.write_videofile(output_file, codec='libx264')

        print(f"Conversion completed successfully! Saved as '{output_file}'")
    except Exception as e:
        print(f"Error during conversion: {e}")

if __name__ == "__main__":
    input_filename = "Input_video.avi"    # Replace with the name of your input .avi file
    output_filename = "output_video.mp4"  # Replace with the desired name for the output .mp4 file

    avi_to_mp4(input_filename, output_filename)

```

## Step 3(optional):
```python

```
