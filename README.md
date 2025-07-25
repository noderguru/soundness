# ⚡ Soundness CLI: Установка и восстановление ключа из мнемоники и получение роли OG

Если раньше вы привязывали в ДС в ветке "https://discord.com/channels/1341336526713257984/1352604755712671814" твиттер, телеграмм и паблик кей то у вас должна быть роль ""onboarded""

чтоб выполнить свой первый zk-proof в Soundness вам нужно получить одну из ролей в дискорд сервере. 24/07/20225 они рандомно выдали следующие роли у кого уже была ""onboarded"":

<img width="520" height="218" alt="image" src="https://github.com/user-attachments/assets/5f7c3334-59d6-4a8f-accb-58623a5939e3" />

переходим в ветку ```game-arena``` https://discord.com/channels/1341336526713257984/1391039818988916768  вводим команду ""/8queens"" нам выдаст линк, переходим и расставляем шахматы в следующем порядке:

<img width="1301" height="865" alt="image" src="https://github.com/user-attachments/assets/fe80868b-c635-42f4-8576-47ca422e6ce9" />


Затем возвращаемя в ДС и в личных сообщениях вам напишет бот ```Sound_Game```


<img width="684" height="462" alt="image" src="https://github.com/user-attachments/assets/7a83f421-6cc5-479e-a68b-85354f6955cb" />

нажимаем ```Generate proof``` после 20-60 сек. ожидания получите следующее сообщение 

<img width="739" height="734" alt="image" src="https://github.com/user-attachments/assets/196cd86c-c1ff-4502-a474-848dc8bd201d" />

Затем нам надо отправить пруф через командную строку (не обязательно сервер арендовать, можно через https://github.com/codespaces), далее будем ставить клиент, библиотеки и прочую историю...

```bash
sudo apt update
sudo apt install -y curl git build-essential pkg-config libssl-dev
```
```bash
curl https://sh.rustup.rs -sSf | sh -s -- -y
source $HOME/.cargo/env
````
```bash
git clone https://github.com/SoundnessLabs/soundness-layer.git
cd soundness-layer/soundness-cli
cargo install --path . --force
```
```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
Так как у вас есть уже мнемоника когда вы генерили паблик кей, но файл ```key_store.json``` с большой долей вероятности вы не сохранили, то его надо восстановить (благо в версии 0.1.2 от 25.07.25 они это реализовали).

## 🔐 Восстановление ключа из мнемоники

```bash
soundness-cli import-key --name <key-name> --mnemonic "<твой мнемоник через пробелы>"
```
Тебя попросят ввести пароль — он будет использоваться для шифрования приватника. Сохрани его обязательно.

<img width="1899" height="187" alt="image" src="https://github.com/user-attachments/assets/56011a58-5bec-4638-8ed5-c5a5962598fb" />

После того как мы восстановили наш файл json надо отправить proof командой которую нам выдал бот из ДС ""🔧 Ready-to-Submit to Soundness Layer Command" и в этой команде подставить имя которое мы указывали ```<key-name>```

<img width="1886" height="618" alt="image" src="https://github.com/user-attachments/assets/c712cd73-46fe-43f8-bbcc-840da10afa53" />












