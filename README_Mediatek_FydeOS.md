# Atualização de Firmware Mediatek no FydeOS

> **Resumo:**  
> Se o Wi-Fi não aparece no FydeOS, é provável que a placa **Mediatek MT7921** não tenha drivers instalados. Este guia mostra como adicionar o firmware correto.

---

## 📌 Passos para Atualizar o Firmware

### 1. Ativar o Modo Desenvolvedor

Ative o modo desenvolvedor nas configurações do FydeOS e reinicie o sistema.

```bash
Ctrl + Alt + T  # Abre o terminal
shell
sudo -i
```

---

### 2. Desabilitar a Verificação de Sistema

```bash
/usr/sbin/crossystem_mode-switch.sh disable-rootfs-verification
```

---

### 3. Remontar o Sistema de Arquivos

```bash
sudo mount -o remount,rw /
```

---

### 4. Baixar e Copiar os Arquivos de Firmware

Acesse o repositório oficial da Mediatek:

🔗 [Repositório Mediatek no kernel.org](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/tree/mediatek)

Baixe os seguintes arquivos:

```bash
WIFI_MT7961_patch_mcu_1_2_hdr.bin
WIFI_RAM_CODE_MT7961_1.bin
BT_RAM_CODE_MT7961_1_2_hdr.bin
```

Depois, copie para a pasta de firmware:

```bash
cd /home/chronos/user/MyFiles/Downloads

sudo cp WIFI_MT7961_patch_mcu_1_2_hdr.bin /lib/firmware/mediatek
sudo cp WIFI_RAM_CODE_MT7961_1.bin /lib/firmware/mediatek
sudo cp BT_RAM_CODE_MT7961_1_2_hdr.bin /lib/firmware/mediatek
```

---

### 5. Ajustar Permissões

```bash
sudo chown root:root /lib/firmware/mediatek/*
```

---

### 6. Reiniciar o Sistema

```bash
sudo reboot
```

---

## 🔗 Créditos

Autor: [Juniordss no Pastebin](https://pastebin.com/u/Juniordss)  
Imagem: ![perfil](https://pastebin.com/cache/img/25/2/20/8453956.jpg)
