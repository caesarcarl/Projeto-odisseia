# Arquitetura do Odisseia

## Visão em camadas

```text
┌────────────────────────────────────────────┐
│ Experiência Odisseia                      │
│ Launcher • Kiosk • Lock • Branding        │
├────────────────────────────────────────────┤
│ Atena IA / ferramentas / automação         │
├────────────────────────────────────────────┤
│ XFCE • shell • aplicações Linux            │
├────────────────────────────────────────────┤
│ Kali/NetHunter ARMHF em chroot              │
├────────────────────────────────────────────┤
│ Android modificado • Magisk • bridges      │
├────────────────────────────────────────────┤
│ Kernel Samsung / drivers Qualcomm          │
├────────────────────────────────────────────┤
│ Galaxy A11 • SDM450 • display • touch      │
└────────────────────────────────────────────┘
```

O modo Cyberdeck prioriza hardware utilizável hoje. O Android funciona como camada de habilitação dos drivers difíceis de substituir, enquanto Linux fornece filesystem, shell, pacotes e desktop.

## Ramo Native

```text
Bootloader Samsung/Qualcomm
          ↓
Android Boot Image v2
          ↓
kernel Samsung + DTB stock
          ↓
initramfs Odisseia
          ↓
userspace Linux mínimo
          ↓
rootfs Linux ARM64 (meta de evolução)
```

O ramo Native é separado do ambiente demonstrável. Isso permite pesquisar boot Linux sem sacrificar a plataforma que já funciona como cyberdeck.

## Recuperação como arquitetura

Firmware stock, PIT, imagens críticas, hashes, Download Mode e checkpoints são tratados como componentes do laboratório. Recuperação não é um plano improvisado depois da falha.
