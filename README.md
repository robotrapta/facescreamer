# FaceScreamer - A Spooky Halloween Computer Vision Project

This is Jacqueline.  She watches everybody walking by, and if she seems something interesting, she'll react.

![Jacqueline](media/jacqueline.jpeg)

It's super simple to adjust what she reacts to, but currently she's programmed to react to:

- **Dogs** - She'll make a snarky comment, or maybe play some animal noises.
- **Baby Strollers** - She'll say something slightly menacing like "Ooooh a baby!"
- **People taking photos** - She will make a snarky comment.
- **People pointing at her** - She will make a snarky comment.

Last year if she got really riled up she'd blast you with a fog machine (DMX-controlled) but it seems I forgot to push that code to github after halloween, so it's lost on some micro-SD card somewhere in my house.  I'll just rewrite it.

## System Setup

Install poetry if you haven't:

```bash
curl -sSL https://install.python-poetry.org | python3 -
export PATH="$HOME/.local/bin:$PATH"
```

Make sure you have the right prerequisites installed.  For Ubuntu:

```bash
sudo apt install -y libgl1-mesa-glx ffmpeg tmux
```

Install python dependencies

```bash
poetry install
```

### Camera setup

Create a default camera config and confirm that it works.

```
poetry run framegrab autodiscover > camera.yaml
poetry run framegrab preview ./camera.yaml
```

### Running automatically

Add something like this to your crontab:
(Update the directory to be what you think it should be.)

```
@reboot $HOME/facescreamer/onboot.sh
```

## Running

Get a [Groundlight API token](https://code.groundlight.ai/python-sdk/docs/getting-started/api-tokens)
and set it as an environment variable like

```bash
export GROUNDLIGHT_API_TOKEN=api_2Q...
```

Then run

```bash
poetry run python ./screamer.py
```

### What to do?

Try looking at the camera and sticking out your tongue.
