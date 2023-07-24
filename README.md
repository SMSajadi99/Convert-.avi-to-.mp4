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

## Step 3(optional - Crop Video):
```python
from moviepy.editor import VideoFileClip
from datetime import time

def crop_video(input_file, output_file, start_hour, start_minute, start_second, end_hour, end_minute, end_second):
    try:
        # Load the video file
        clip = VideoFileClip(input_file)

        # Calculate the start and end time in seconds
        start_time = time(hour=start_hour, minute=start_minute, second=start_second)
        end_time = time(hour=end_hour, minute=end_minute, second=end_second)
        start_time_seconds = start_time.hour * 3600 + start_time.minute * 60 + start_time.second
        end_time_seconds = end_time.hour * 3600 + end_time.minute * 60 + end_time.second

        # Set the output file format to mp4 and save the cropped video
        cropped_clip = clip.subclip(start_time_seconds, end_time_seconds)
        cropped_clip.write_videofile(output_file, codec='libx264')

        print(f"Cropping completed successfully! Saved as '{output_file}'")
    except Exception as e:
        print(f"Error during cropping: {e}")

if __name__ == "__main__":
    input_filename = "People on the Street_ What is Power.avi"    # Replace with the name of your input video file
    output_filename = "output_video.mp4"  # Replace with the desired name for the output video file

    # Input the start time from the user
    start_hour = int(input("Enter the start hour (0-23): "))
    start_minute = int(input("Enter the start minute (0-59): "))
    start_second = int(input("Enter the start second (0-59): "))

    # Input the end time from the user
    end_hour = int(input("Enter the end hour (0-23): "))
    end_minute = int(input("Enter the end minute (0-59): "))
    end_second = int(input("Enter the end second (0-59): "))

    crop_video(input_filename, output_filename, start_hour, start_minute, start_second, end_hour, end_minute, end_second)

```
