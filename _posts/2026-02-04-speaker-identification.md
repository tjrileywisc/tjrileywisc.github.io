---
title: Speaker identification
date: 2026-02-04
categories: [python]
tags: []
---

I've been playing around with [WhisperX](https://github.com/m-bain/whisperX) and a project idea I've had for a while. It's unfortunate that so many 
decisions that most impact our lives is made at the level of government with the least oversight - the local level. Our built environment is largely
left to local government, which affects the quality of our schools and our local economy (among many other things), but they also get the least attention.

My hometown has had a newspaper start up in the past year, which has been doing well as I understand, but the details of city government meetings aren't
fully captured in an article.

I've been thinking of a tool which would attribute speech in city government meetings to the government official who said it. Not only would you have
to transcribe the speech, but you'd have to get the second-by-second breakdown of who was speaking, and how they can be uniquely identified from others who spoke.

I'm just using an off the shelf diarization and transcription model for this at the moment. The missing piece not provided in WhisperX (or [pyannote](https://github.com/pyannote/pyannote-audio)) was a way to match the identified speakers between meetings. `pyannote` will just give you the segmented results (for example, `SPEAKER_00` or `SPEAKER_01`). It does fortunately give you the embedding vectors it associated with each speaker.


The approach I settled on was saving the python dictionary of speakers and vectors and using cosine similarity to match them. No idea yet if this is the best approach,
or if my threshold setting is correct, but I pushed up a [commit](https://github.com/tjrileywisc/waltham-comments/commit/bfcb56f6cdb9a4c5bdc9fcd2387d0a99aafeb289) to my repo.
