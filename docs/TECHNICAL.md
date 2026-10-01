# Notas técnicas

## Plataforma Mobile

- Dispositivo: Samsung Galaxy A11 SM-A115M (`a11q`)
- SoC: Qualcomm SDM450 / família MSM8953
- CPU: 8 × Cortex-A53
- Hardware: ARMv8 / capacidade ARM64
- Ambiente operacional do MVP: Android modificado + Magisk + Kali/NetHunter ARMHF em chroot + XFCE
- Exibição: TigerVNC / KeX
- Entrada: mini teclado 2.4 GHz via USB OTG

## Boot e reversal

A análise documentada identificou Android Boot Image v2, kernel, ramdisk e um blob multi-DTB. O laboratório preserva firmware stock, PIT e hashes antes de modificações.

## Software próprio

- **Shell:** boot, chroot, VNC, watchdog, branding, kiosk, manutenção e rollback.
- **Python:** parsers, diagnóstico, relatórios e automações.
- **C/C++:** utilitários e experimentos de userspace/framebuffer.
- **Java/Android:** launcher, HOME customizado, kiosk, lockscreen e integração com o ambiente Linux.

## Estabilização gráfica

A investigação do KeX/VNC separa falha de viewer, servidor e chroot. Entre as medidas experimentadas estão framebuffer fixo, bloqueio de resize remoto, compositor XFWM desativado e reinício serializado.

## Regra de publicação

Não classifique como “concluído” algo que só existe como código. Diferencie:
1. ideia;
2. código implementado;
3. teste isolado;
4. teste integrado;
5. uso prolongado em hardware.
