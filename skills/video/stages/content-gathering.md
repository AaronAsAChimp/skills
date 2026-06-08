# Content gathering

In this stage you will be assisting in gathering or generating the content for the video and putting it in the `assets/` folder.

- Use all of the production documents that have been created so far
- Review these documents to identify any possible production issues
- Iterate on the content to resolve these issue, stopping to check in before each iteration
- Determine what content will be shot, generated with AI, etc.
- All assets must have the requried licenses if it was gathered externally. This includes:
  - Stock imagery and other assets
  - Music
  - Brands and trademarks
- Produce the shot list, include:
  - A shot number and slug
  - what needs to be shot
  - shoot location
  - time of day or lighting constraints (if applicable)
  - the equipment need for that shot
  - how long the shot should approximately be
  - The people needed for each shot: talent, crew, etc.
  - Backup options
- The files should be named like so:
  - shot list: `assets/shotlist.md`
  - for shots and vo: `assets/shot-[shot number]-take-[take-number]-[slug].[ext]`
  - for b-roll: `assets/shot-[shot number]-[slug].[ext]`
  - for other assets: `assets/shot-[shot number]-[slug]-[asset description].[ext]`
- If you find assets in the `assets/` folder that do not match the naming convention ask if they should be renamed or if you should just add a note to the production documents.

If the skill is available, use `/remotion-best-practices` to help generate any assets needed.

You can use the command `ffmpeg` or `mediainfo` to inspect assets.

## Success criteria

- [ ] No scheduling conflicts with talent, crew, or other resources needed for the video.
- [ ] Audio is present and back up audio is available
- [ ] Room tone has been recorded for each shot location
- [ ] Assets have been reviewed for any legal, licensing, or permission/release issues.
- [ ] All of the shots are present in the `assets/` folder and within +/- 10% of their target time.
- [ ] All graphics and animations are present in the `assets/` folder and within +/- 10% of their target time.
- [ ] All voice overs and music is present in the `assets/` folder and within +/- 10% of their target time.


Example `assets/shotlist.md`:

```md
# Shotlist

## Shots

- Shot 1 - [slug] - Time [hh:mm:ss]
	- Location: [location] [time of day]
	- Talent: [person 1], [person 2], ...
	- Crew: [person 1] [role], [person 2] [role], ...
	- Equipment: [thing 1], [thing 2]
	- Back up options: [option 1]
	- [link to asset]
- [...]

## Additional assets

- For shot 1 - [asset description]
	- [person responsible] [role]
	- [link to asset]
- For shot 2 - [...]
	- [...]
```
