/**
 * TypeScript — язык программирования, выпущен в релиз Microsoft в 2012 году
 * как средство разработки веб-приложений, расширяющее возможности JavaScript.
 *
 * TS - это компилируемый язык, который по сути является надстройкой над языком JS.
 * Поэтому для комфортного изучения TypeScript студент должен быть знаком с языком JavaScript.
 *
 * Браузеры не умеют читать файлы .ts, поэтому компилятор преобразует .ts файлы в .js,
 * предварительно проведя статическую проверку типов static type checking
 *
 * Статическая проверка типов - это проверка еще до исполнения скрипта конечным пользователем.
 * в TS она происходит либо при компиляции .ts в .js, либо с помощью плагинов в популярных IDE
 *
 */

function example1() {
    // JS - язык с динамической типизацией, типы могут меняться во время выполнения скрипта
    let firstName = 'Sergey';

    const str1 = firstName.toUpperCase();
    console.log('firstName', firstName);
    console.log('str1', str1);

    // -> firstName Sergey
    // -> str1 SERGEY

    /**
     * А значит, если мы изменим внутри кода тип переменной firstName на числовой,
     * то в результате исполнения следующего кода получим ошибку
     * (Так как метод toUpperCase работает только для строк)
     * Ошибку будет не видно, пока кто-то (вы или ваш пользователь) не исполнит скрипт в браузере
     */

    firstName = 12345;
    const str2 = firstName.toUpperCase();
    // Uncaught TypeError: firstName.toUpperCase is not a function
    console.log('firstName', firstName);
    console.log('str2', str2);


    const age = 31;
    const str3 = age.toUpperCase();
    // Uncaught TypeError: age.toUpperCase is not a function
    console.log('age', age);
    console.log('str2', str3);
}

example1()



/**
 * Так же статическая проверка типов может пригодиться нам, если мы захотим избежать ненужных опечаток
 */
function example2() {
    const user = {
        firstName: 'Sergey',
        lastName: 'Fegon',
        role: 'programmer'
    }

    console.log(`${user.firstName} ${user.lastName} is a ${user.role}`)
    // -> Sergey Fegon is a programmer

    /**
     * Давайте сознательно допустим опечатку в поле firstName,
     * причем такую, которую очень легко сделать и трудно уловить глазами
     */
    console.log(`${user.fristName} ${user.lastName} is a ${user.role}`)
    // -> undefined Fegon is a programmer
}

example2()


/**
 * Давайте перенесем наш код в официальную песочницу TypeScript,
 * пока еще мы не научились запускать .ts файлы на нашей машине.
 * Этому мы научимся в следующих уроках
 * https://www.typescriptlang.org/play
 */


/**
 * Мы видим, что песочница TS еще до запуска нашего кода кнопкой Run выдала нам несколько ошибок
 * Рассмотрим их поподробнее...
 */


/**
 * Таким образом мы еще на этапе написания кода можем предусмотреть и предотвратить ошибки несоответствия типов
 * Современные редакторы, например VS Code имеют встроенную поддержку typescript'а,
 * что позволяет отлавливать такие ошибки на лету.
 * А так же использование TS очень сильно прокачивает автодополнение кода вашего редактора и IDE.
 * Редактор использует описанные вами типы, чтоб предлагать к примеру поля у объектов.
 * Все это мы рассмотрим в дальнейших уроках.
 */