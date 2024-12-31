
- ***Layers of Mobile App Architecture***:
    - **Presentation Layer**: This is the front end, or the UI, that users interact with. It includes the views, layouts, and logic to present data.
    - **Business Logic Layer (BLL)**: This layer manages the app's core functionality and processes. It connects the UI to the data layer and enforces business rules, data manipulation, and decision-making logic.
    - **Data Access Layer (DAL)**: This layer manages all data-related tasks, like data retrieval, storage, and caching, and communicates with the backend and databases.
    
- ***Common Mobile App Architecture Patterns***:
    - **MVC (Model-View-Controller)**: Separates the app’s logic into the model (data), view (UI), and controller (interaction logic). MVC is common in web-based mobile apps.
    - **MVVM (Model-View-View Model)**: Often used in native apps, this pattern separates UI code (View) from the data handling logic (View Model), which interacts with the Model (data layer).
    - **Clean Architecture**: This architecture pattern organizes the app into layers to improve testability and scalability, often structuring apps with use cases and entities to define business rules.