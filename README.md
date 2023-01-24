# youtube_playlist_downloader

import os
import youtube_dl

# Replace the following line with the actual path of the directory where you want to save the videos
directory = 'C:\\Users\\tripa\\Music\\BS-GOLAND'

if not os.path.exists(directory):
    os.makedirs(directory)

# Replace the following line with the actual URL of the playlist
playlist_url = 'https://www.youtube.com/playlist?list=PLWdjt3AssDL5PF_A_AF3PSRkg12r5wdsO'

ydl_opts = {
    'format': 'bestvideo[ext=mp4]+bestaudio[ext=m4a]/best[ext=mp4]/best',
    'outtmpl': f'{directory}\\%(playlist_index)s - %(title)s.%(ext)s',
    'noplaylist': False
}

with youtube_dl.YoutubeDL(ydl_opts) as ydl:
    ydl.download([playlist_url])
