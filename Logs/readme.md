# EVTXs

# To Prepare

```powershell
wget -useb https://gist.githubusercontent.com/Purp1eW0lf/e0b757e66d5da629c1d03e2941fa5b4b/raw/098f624370b9a096e0ef7d32ca71b11e183266ae/Pull_logs_and_zip.ps1 -outfile Pull_logs_and_zip.ps1
```
<img width="700" alt="image" src="https://user-images.githubusercontent.com/44196051/171155030-0c4219f5-1782-4c16-bef2-eaa08ed0b6f8.png">ii 

Pull chainsaw binary
https://github.com/countercept/chainsaw/releases/tag/v1.1.7

# Chainsaw

```bash
chainsaw hunt ./Collected_Data --rules ./sigma_rules/ --mapping ./mapping_files/sigma-mapping.yml --full --lateral-all --col-width 100
```

<img width="1126" alt="image" src="https://user-images.githubusercontent.com/44196051/171155423-926b881d-db8b-4428-8916-9b1bff3e8e2a.png">
