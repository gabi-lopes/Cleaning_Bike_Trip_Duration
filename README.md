# 🚴 Análise de Duração de Viagens  
**Autora:** Gabriela Lopes  

---

## 📖 Introdução  
Este projeto analisa dados de duração de viagens de um sistema de compartilhamento de bicicletas na região da Baía de São Francisco. O dataset contém informações sobre duração das viagens, estações de partida/chegada, dados demográficos dos usuários e participação em programas de bicicletas compartilhadas.  

O objetivo é explorar a duração das viagens, comportamento dos usuários e padrões geográficos, além de limpar e visualizar os dados para extrair insights significativos.  

---

## 🗂 Dataset  
**Arquivo:** `201902-fordgobike-tripdata.csv`  
**Linhas:** 183.412  
**Colunas:** 16  

| Feature | Descrição |
|---------|-----------|
| `duration_sec` | Duração da viagem em segundos |
| `start_time` | Hora de início da viagem |
| `end_time` | Hora de término da viagem |
| `start_station_id` | ID da estação de partida |
| `start_station_name` | Nome da estação de partida |
| `start_station_latitude` | Latitude da estação de partida |
| `start_station_longitude` | Longitude da estação de partida |
| `end_station_id` | ID da estação de chegada |
| `end_station_name` | Nome da estação de chegada |
| `end_station_latitude` | Latitude da estação de chegada |
| `end_station_longitude` | Longitude da estação de chegada |
| `bike_id` | ID da bicicleta utilizada |
| `user_type` | Tipo de usuário (Subscriber ou Customer) |
| `member_birth_year` | Ano de nascimento do usuário |
| `member_gender` | Gênero do usuário |
| `bike_share_for_all_trip` | Participação no programa “Bike Share for All” |

---

## 🔍 Features de Interesse  
O foco principal da análise está em:  
- **Duração da viagem (`duration_sec`)** – para analisar o tempo das viagens.  
- **Estações de início e fim** – para identificar rotas e estações mais populares.  
- **Demografia dos usuários (`user_type`, `member_birth_year`, `member_gender`)** – para entender quem utiliza o serviço.  

Outras variáveis de apoio incluem `start_time`, `end_time` e coordenadas das estações para análise temporal e geográfica.  

---

## 🧹 Limpeza de Dados  
- Outliers em `duration_sec` acima de 769 segundos (percentil 75) foram removidos.  
- Linhas com valores faltantes em `member_gender` foram excluídas.  
- Dataset final limpo contém **134.395 linhas**.  

```python
df_cleaned.to_csv('cleaned_data.csv', index=False)
