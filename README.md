## linux-gerar-senhas

**Comandos no linux para se criar senhas aleatórias com 14 caracteres:**

```bash
cat /dev/urandom | tr -dc 'a-zA-Z0-9-_!@#$%&*+?' | fold -w 14 | head -n1

cat /dev/urandom | tr -cd [:graph:] | head -c 14

cat /dev/urandom | base64 -w 0 | fold -w 14 | head -1

xxd -l7 -p /dev/urandom

openssl rand -hex 7

openssl rand -base64 12 | head -c 14

echo "Uma frase que você conheça!" | md5sum | base64 | rev | head -c 14

XXX=$(echo "Uma frase que você conheça!" | md5sum | base64); XXX2=$(cat /dev/urandom | tr -dc '_!@#$%&*+?' | fold -w 1 | head -1); XXX3=$(cat /dev/urandom | tr -dc '_!@#$%&*+?' | fold -w 1 | head -1); echo "${XXX2}${XXX:0:6}${XXX3}${XXX:7:6}"
```
