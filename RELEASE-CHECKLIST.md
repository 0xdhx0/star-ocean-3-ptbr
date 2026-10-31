# Checklist de lançamento

1. Gerar as ISOs traduzidas dos dois discos (conferência "0 falhas", nenhuma entrada realocada).
2. Testar no PCSX2 com o jogo reiniciado: título, novo jogo, primeira cena, menu, uma batalha, salvar e carregar e, no
   disco 2, a troca de disco.
3. Gerar os patches:
   `xdelta3 -e -9 -s "<ISO original>" <ISO traduzida> SO3_PTBR_DiscoN.xdelta`
4. Conferir: aplicar cada patch sobre a ISO original e comparar com a ISO traduzida (`cmp` sem diferença).
5. Calcular SHA-256 dos `.xdelta` e CRC32/SHA-1 das ISOs traduzidas e atualizar o README (Download e Instalação).
6. Atualizar "Novidades da vX" no README e o título com a versão.
7. Montar o zip `SO3_PTBR_vX.zip` (pasta `SO3_PTBR_vX/` com LEIA-ME.txt, os dois `.xdelta`, SHA256SUMS.txt e LICENSE.txt), atualizando a versão e os checksums no LEIA-ME.
8. Commit, tag `vX` e Release com o zip anexado. Marcar como pre-release enquanto for beta.
