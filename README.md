# cssMemeSlider
Представляю вашему вниманию CSS Slider. Сдайдер выполнен на чистом css и полностью адаптивен.  
Для данного набора картинок я задал максимальную ширину в 1000px. Сам слайдер ценрируется по горизонтали и имеет отступы сверху и снизу. При уменьшении ширины экрана на брейкпоинте в 700px, нижний блок с цитатами и кнопками контроля слайдера перестраивается в вертикальное положение, а на 500px уменьшается шрифт цитат, при этом картинка подстраивается под размер слайдера.  
Для реализации переключения слайдов использовал тег инпут с типом радио (первый с атрибутом checked, показывает активный слайд при згрузке страницы) и привязаные к ним теги label c атрибутом for для привязки конкретного элемента формы. В последствии мы скрыли все инпуты(радио) и вместо них в тегах label мы создали свои собственные элементы управления слайдером.  
Далее мы расположили картинки и подписи в ряд использую flex. И изначально первый слайд имеет атрибут checked и его смещение по Х составляет ноль. При присваивании атрибута checked второму элементу он имеет смещение по Х -100%, третему -200% и т.д. Очень важно отметить что ипут с типом радио имеет только одно возможное аттивное состояние, благодаря этому мы можем переключатся между элементами. Поиск нужного элемента отображения происходит  при помощи селектора "~". Вот к примеру:  
`#slide2:checked ~ .img-container .slide,  
#slide2:checked ~ .bottom-container .text-container .text  
{  
    transform: translateX(-100%);  
}`  
Это можно прочитать следующим образом, если выбран второй инпут-радио(которые мы ранее благопалучно заменили на новые через label-for), то в html разметке следующий за инпутом-радио .img-container а внем находящийся .slide и таким же образом подпись к слайду сместятся влево на ширину равную 100%.  
Далее таким же образом были стилизованы кнопки управления слайдером и их поведение. Отдельно хочу обратить внимание на использование уточнения для применение некоторых стилистических свойств к отдельно выбраным label c помощью label[for="slide1"] к примеру.  
Все блоки/составные части слайдера (контролы, картинки, подписи к слайдеру) находятся в базовом потоке дом-элементов и реализации слайдера не используются запретные приемы описанные в ТЗ.  
<br>
Спасибо если дочитали до конца и за объективную проверку, удачи в обучении и хорошего дня...  