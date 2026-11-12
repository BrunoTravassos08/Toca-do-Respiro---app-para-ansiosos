# Toca do Respiro

App Android para respirar com calma junto com um coelhinho. Feito para quem convive com ansiedade.

**Baixar o app:** [toca-do-respiro.apk](https://github.com/BrunoTravassos08/Toca-do-Respiro---app-para-ansiosos/releases/latest/download/toca-do-respiro.apk)

## O que o app faz

- Contagem de 3 segundos antes de começar
- Coelhinho que inspira e expira com você, com frases de apoio
- Medidor de segundos de cada fase
- Modo noite, com o coelhinho na toca
- Modo chuva, com som de chuva suave
- Som do ritmo e tempo de cada fase ajustáveis
- Sessões de 1 minuto, 3 minutos ou tempo livre
- Tela deitada em tela cheia

## Como o APK é gerado

O app é a página `www/index.html` empacotada com [Capacitor](https://capacitorjs.com/).
O APK não é gerado automaticamente. Quando as alterações estiverem prontas e testadas,
abra **Actions > Gerar APK > Run workflow** (branch `main`). O GitHub Actions
(`.github/workflows/apk.yml`) gera o APK e publica uma nova versão em **Releases**. O link acima sempre aponta para a mais recente.

Para que o Android aceite atualizações, o APK é assinado com a chave guardada nos segredos
do repositório `KEYSTORE_BASE64` e `KEYSTORE_PASSWORD`. Sem eles, é gerado um APK de teste.

Para gerar localmente (precisa do Android Studio/SDK):

```bash
npm ci
npx cap sync android
cd android && ./gradlew assembleDebug
```
