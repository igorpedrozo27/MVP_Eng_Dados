# Catálogo de Dados

| Nome da Coluna          | Tipo de Dado | Descrição                                                                 |
|------------------------|--------------|---------------------------------------------------------------------------|
| track_id               | string       | Identificador único da faixa.                                             |
| track_name             | string       | Nome da faixa musical.                                                    |
| track_number           | string       | Posição da faixa dentro do álbum ao qual pertence.                        |
| track_popularity       | int          | Métrica que representa o grau de popularidade da faixa entre os ouvintes, expressa como um valor inteiro. Essa métrica é calculada com base no volume e na recorrência de reproduções, considerando especialmente a performance recente da faixa. Valores mais altos indicam maior popularidade. |
| track_duration_ms      | int          | Duração da faixa em milissegundos.                                        |
| explicit               | string       | Indica se a faixa contém conteúdo explícito.                              |
| artist_name            | string       | Nome do artista intérprete da faixa.                                      |
| artist_popularity      | string       | Métrica que representa o grau de popularidade do artista entre os ouvintes, expressa como um valor inteiro. É calculada a partir da popularidade agregada de suas faixas, considerando volume de reproduções e engajamento recente. Valores mais altos indicam maior popularidade. |
| artist_followers       | int          | Número de ouvintes que seguem o artista.                                  |
| artist_genres          | string       | Estilos ou categorias musicais associadas ao artista.                     |
| album_id               | string       | Identificador único do álbum.                                             |
| album_name             | string       | Título do álbum do qual a faixa faz parte.                                |
| album_release_date     | string       | Data de lançamento do álbum.                                              |
| album_total_tracks     | string       | Número total de faixas presentes no álbum.                                |
| album_type             | string       | Tipo ou natureza do álbum, como single, EP ou álbum completo.             |
