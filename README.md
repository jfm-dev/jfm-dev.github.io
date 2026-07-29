# jfm-dev.github.io — site Fluxe

Site simples e estático para:
- Servir `app-ads.txt` (validação AdMob) em `/app-ads.txt`
- Página inicial com descrição da app
- Política de privacidade em `/privacidade.html`

## Estrutura
```
index.html          # página inicial
privacidade.html     # política de privacidade
app-ads.txt          # linha do AdMob
style.css            # estilo partilhado
```

## Publicar no GitHub Pages (site de utilizador)

Este repositório tem de se chamar exatamente **`jfm-dev.github.io`** — é o nome especial que o GitHub reconhece para publicar automaticamente na raiz do domínio `https://jfm-dev.github.io/` (sem isto o `app-ads.txt` não fica na raiz do domínio, e o AdMob não valida).

```
cd fluxe-site
git init
git add .
git commit -m "Site inicial da Fluxe"
git branch -M main
git remote add origin https://github.com/jfm-dev/jfm-dev.github.io.git
git push -u origin main
```

Se o repositório `jfm-dev.github.io` ainda não existir no GitHub:
1. Vai a https://github.com/new
2. Nome do repositório: `jfm-dev.github.io` (exatamente assim)
3. Público, sem README/gitignore (já temos ficheiros locais)
4. Cria, depois corre os comandos acima.

O GitHub Pages fica ativo automaticamente para repositórios `<user>.github.io` (não precisa de configurar nada em Settings → Pages, mas confirma lá que está "Deployed from branch: main / (root)").

Demora 1-2 minutos a ficar disponível em `https://jfm-dev.github.io/`.

## Depois de publicar

1. Confirma que `https://jfm-dev.github.io/app-ads.txt` abre e mostra:
   `google.com, pub-5566356063032273, DIRECT, f08c47fec0942fa0`
2. Cola `https://jfm-dev.github.io` em **Play Console → Presença na loja → Ficha da loja principal → Website**.
3. A validação no AdMob pode demorar até 24h a atualizar.

## Atualizar mais tarde
```
git add .
git commit -m "Atualiza site"
git push
```

## (Alternativa) Firebase Hosting
Os ficheiros `firebase.json` e `.firebaserc` ficaram no repositório caso queiras voltar a hospedar no Firebase Hosting em vez do GitHub Pages — nesse caso corre `npx firebase-tools deploy --only hosting` (aponta para o projecto `fluxe-acedb`).
