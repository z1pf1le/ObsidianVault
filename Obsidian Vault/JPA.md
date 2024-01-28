[[ORM]]

Java Persistence API - это спецификация (стандарт, технология), обеспечивающая объектно-реляционное отображение простых JAVA-объектов (Plain Old Java Object - POJO) и предоставляющая универсальный API для сохранения, получения и управления такими объектами.

Сам JPA не умеет ни сохранять, ни управлять объектами, JPA только определяет правила игры: как должен действовать каждый провайдер (Hibernate, EclipseLink, OJB, Torque и т.д.), реализующий стандарт JPA. Для этого JPA определяет интерфейсы, которые должны быть реализованы провайдерами. Также JPA определяет правила, как должны описываться метаданные отображения и как должны работать провайдеры.

Каждый провайдер обязан реализовывать всё из JPA, определяя стандартное получение, сохранение и управление объектами. Помимо этого, провайдеры могут добавлять свои личные классы и интерфейсы, расширяя функционал JPA.

JPA:

- API в пакете javax.persistance (набор интерфейсов EntityManager, Query,EntityTransaction),
- JPQL - объектный язык запросов (запросы выполняются к объектам)
- Metadata (аннотации или xml)

JAVA-код, написанный только с использованием интерфейсов и классов JPA, позволяет разработчику гибко менять одного провайдера на другого. Например, если приложение использует Hibernate как провайдера, то ничего не меняя в коде можно поменять провайдера на любой другой. Но, если мы в коде использовали интерфейсы, классы или аннотации, например, из Hibernate, то поменяв провайдера на EclipseLink, эти интерфейсы, классы или аннотации уже работать не будут.