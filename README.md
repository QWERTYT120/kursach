<table style="width: 100%;">
  <tr>
    <td style="text-align: center; border: none;">
    Министерство образования и науки РФ<br>
Государственное бюджетное профессиональное образовательное учреждение Республики Марий Эл<br>
Йошкар-Олинский технологический колледж
</td>
  </tr>
  <tr>
    <td style="text-align: center; border: none; height: 15em;">
    <h2 style="font-size:3em;">Отчет</h2>
      <h3>по курсовой работе<br><br> по дисциплине "Проект и дизайн ИС Т"<br><br> Тема:<b> "Запись к врачу"<b> </h3></td>
  </tr>
  <tr>
    <br><br><td style="text-align: right; border: none; height: 20em;">
      Разработал:<br/>
      Проулкин Алексей<br>
      Группа: И-31<br>
      Преподаватель:<br>
      Колесников Евгений Иванович
    </td>
  </tr>
  <tr>
    <td style="text-align: center; border: none; height: 5em;">
    г.Йошкар-Ола,<br> 2021</td>
  </tr>
</table>

<div style="page-break-after: always;"></div>

# Описание предметной области
![de8e4e7fb3879b3ec565a50a940242e9525ec776](https://user-images.githubusercontent.com/78725341/132938991-9439408e-3084-4f51-b088-0ddef2981714.jpg)

  Наше медицинское учреждение имеет штат специалистов, которые занимаются приёмом пациентов по предварительной записи. Оплата приема осуществляется после получения амбулаторной карты, которая оформляется в регистратуре. Информация о каждом пациенте хранится в базе данных больницы, поэтому имеется возможность проследить за всеми посещениями выбранного пациента данной клиники. 

Перед приемом в больницу пациент проходит регистрацию. Если пациент уже был на приеме в данной больнице, тогда проводится поиск по базе и данного пациента записывают на прием и выдают амбулаторный лист. В амбулаторном листе указывается в какое время и на который день назначен прием, к какому специалисту (специализация, фамилия врача), в каком кабинете будет осуществляться прием, стоимость приема и пометка оплачен прием или нет. Если же пациент впервые в данной больнице, тогда ему присваивается уникальный регистрационный номер, заносятся в базу данных (фамилия, имя и отчество, адрес и дата рождения), а затем уже происходит запись на прием к конкретному врачу и на конкретное время и выдается амбулаторный лист. Пациент должен быть зарегистрирован в системе до приема в больнице.

Один пациент может быть записан на прием к нескольким врачам, каждому приему назначается уникальный номер. Каждый врач может просмотреть расписание приемов на любой из выбранных дней.

После регистрации пациента, в назначенный день и время он приходит на прием к специалисту. Врач осуществляет поиск и выбор данного пациента, выбирает прием, и исходя из выбранного приема, делает запись о диагнозе и назначении лечения данному пациенту. При повторном приеме происходит редактирование истории болезни.
   
# Диаграмма прецедентов 
  
  ![14](https://user-images.githubusercontent.com/78725341/133046980-e2f66200-07aa-46ef-848c-885ca745bedd.jpg)
  
   
  
  # Спецификация прецедентов
  
  
  |                        |              |                      
|------------------------|------------  |
|*Прецедент*             | Запись к врачу |
|*Идентификатор*         | ID 1         |
|*Краткое описание*      | Пациент записывает к врачу|
|*Главные акторы*        | Пациент|
|*Второстепенные акторы* | Работник регистратуры |
|*Предусловия*           | Пациент записывается к врачу |
|*Основной поток*        | 1. Прецедент начинается, когда пациент записывается к врачу<br/> 2. Если пациент записывается к другому врачу <br/>&nbsp;&nbsp;&nbsp;&nbsp;2.1 Работник регистратуры назначает другого врача <br/>3. Если пациент записался к врачу<br/>&nbsp;&nbsp;&nbsp;&nbsp;3.1 Работник регистратуры выдает талон |
|*Альтернативные потоки* | 2.1 Работник регистратуры назначает другого врача <br/>3.1 Работник регистратуры выдает талон |
|*Постусловия*           | Пациент записался<br/>Клиент отаказался от записи к врачу |

   |                        |              |                      
|------------------------|------------  |
|*Прецедент*             | Прием врача |
|*Идентификатор*         | ID 2        |
|*Краткое описание*      | Раб. регистрат. назначает приём к врачу |
|*Главные акторы*        | Работник регистратуры |
|*Второстепенные акторы* | Врач |
|*Предусловия*           | Раб.регистрат. назначает приём к врачу  |
|*Основной поток*        | 1. Прецедент начинается, когда раб. регистрат. назначает приём к врачу <br/> 2. Врач осведомлен о приёме |
|*Альтернативные потоки* | нет |
|*Постусловия*           | Раб. рестистрат. назначил приём к врачу |
  
   |                        |              |  
|------------------------|------------  |
|*Прецедент*             | Врач проводит обследование |
|*Идентификатор*         | ID 3       |
|*Краткое описание*      | Врач обследует пациента |
|*Главные акторы*        | Врач |
|*Второстепенные акторы* | Пациент |
|*Предусловия*           | Пациент обследуется у врача  |
|*Основной поток*        | 1. Прецедент начинается, когда врача обследует пациент <br/> 2. Врач ставит диагноз |
|*Альтернативные потоки* | нет |
|*Постусловия*           | Пациент обследовался у врача |
  
  # ER-диаграмма
  
  
![4](https://user-images.githubusercontent.com/78725341/134472165-d1d3b6a6-16e7-4e6f-b813-70b0cf7f6b61.PNG)

