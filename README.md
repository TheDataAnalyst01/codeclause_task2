# codeclause_task2
Speech recognition engine/API support:

CMU Sphinx (works offline)
Google Speech Recognition
Google Cloud Speech API
Wit.ai
Microsoft Azure Speech
Microsoft Bing Voice Recognition (Deprecated)
Houndify API
IBM Speech to Text
Snowboy Hotword Detection (works offline)
Tensorflow
Vosk API (works offline)
OpenAI whisper (works offline)
Whisper API
Quickstart: pip install SpeechRecognition. See the "Installing" section for more details.

To quickly try it out, run python -m speech_recognition after installing.

Project links:

PyPI
Source code
Issue tracker
Library Reference
The library reference documents every publicly accessible object in the library. This document is also included under reference/library-reference.rst.

See Notes on using PocketSphinx for information about installing languages, compiling PocketSphinx, and building language packs from online resources. This document is also included under reference/pocketsphinx.rst.

You have to install Vosk models for using Vosk. Here are models avaiable. You have to place them in models folder of your project, like "your-project-folder/models/your-vosk-model"

Examples
See the examples/ directory in the repository root for usage examples:

Recognize speech input from the microphone
Transcribe an audio file
Save audio data to an audio file
Show extended recognition results
Calibrate the recognizer energy threshold for ambient noise levels (see recognizer_instance.energy_threshold for details)
Listening to a microphone in the background
Various other useful recognizer features
Installing
First, make sure you have all the requirements listed in the "Requirements" section.

The easiest way to install this is using pip install SpeechRecognition.

Otherwise, download the source distribution from PyPI, and extract the archive.

In the folder, run python setup.py install.

Requirements
To use all of the functionality of the library, you should have:

Python 3.8+ (required)
PyAudio 0.2.11+ (required only if you need to use microphone input, Microphone)
PocketSphinx (required only if you need to use the Sphinx recognizer, recognizer_instance.recognize_sphinx)
Google API Client Library for Python (required only if you need to use the Google Cloud Speech API, recognizer_instance.recognize_google_cloud)
FLAC encoder (required only if the system is not x86-based Windows/Linux/OS X)
Vosk (required only if you need to use Vosk API speech recognition recognizer_instance.recognize_vosk)
Whisper (required only if you need to use Whisper recognizer_instance.recognize_whisper)
openai (required only if you need to use Whisper API speech recognition recognizer_instance.recognize_whisper_api)
The following requirements are optional, but can improve or extend functionality in some situations:

If using CMU Sphinx, you may want to install additional language packs to support languages like International French or Mandarin Chinese.
The following sections go over the details of each requirement.

Python
The first software requirement is Python 3.8+. This is required to use the library.

PyAudio (for microphone users)
PyAudio is required if and only if you want to use microphone input (Microphone). PyAudio version 0.2.11+ is required, as earlier versions have known memory management bugs when recording from microphones in certain situations.

If not installed, everything in the library will still work, except attempting to instantiate a Microphone object will raise an AttributeError.

The installation instructions on the PyAudio website are quite good - for convenience, they are summarized below:

On Windows, install PyAudio using Pip: execute pip install pyaudio in a terminal.
On Debian-derived Linux distributions (like Ubuntu and Mint), install PyAudio using APT: execute sudo apt-get install python-pyaudio python3-pyaudio in a terminal.
If the version in the repositories is too old, install the latest release using Pip: execute sudo apt-get install portaudio19-dev python-all-dev python3-all-dev && sudo pip install pyaudio (replace pip with pip3 if using Python 3).
On OS X, install PortAudio using Homebrew: brew install portaudio. Then, install PyAudio using Pip: pip install pyaudio.
On other POSIX-based systems, install the portaudio19-dev and python-all-dev (or python3-all-dev if using Python 3) packages (or their closest equivalents) using a package manager of your choice, and then install PyAudio using Pip: pip install pyaudio (replace pip with pip3 if using Python 3).
PyAudio wheel packages for common 64-bit Python versions on Windows and Linux are included for convenience, under the third-party/ directory in the repository root. To install, simply run pip install wheel followed by pip install ./third-party/WHEEL_FILENAME (replace pip with pip3 if using Python 3) in the repository root directory.

