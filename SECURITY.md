# Segurança

## Segredos

Nunca versione:

- `.env` (token do bot, `WEB_TOKEN` e URLs privadas)
- `cookies.txt` / `*.cookies.txt`
- `data/settings.json`
- logs, dumps e arquivos de sessão

O `.gitignore` já cobre esses arquivos. Se algum token for exposto em um commit,
print, issue ou arquivo compactado, **resete o token imediatamente** no Discord
Developer Portal.

## Painel exposto

- Para uso local ou Activity, o painel pode ficar sem `WEB_TOKEN`.
- Se o painel for exposto na internet sem a Activity, defina `WEB_TOKEN` e use
  `?token=...` ou o header `x-ntfd-token`.
- O proxy de capas só aceita hosts conhecidos (Spotify, YouTube, Deezer,
  Discord e SoundCloud).

## Voz e dados

- O bot só precisa das intents `Guilds` e `GuildVoiceStates`.
- `MessageContent` é opcional e só deve ser ligada se você usar comandos com
  prefixo.
- Cookies do YouTube devem ser de uma conta secundária, nunca da conta
  principal.

## Versões

Use Node.js **22.12+**. Versões antigas podem falhar na voz DAVE do Discord.
