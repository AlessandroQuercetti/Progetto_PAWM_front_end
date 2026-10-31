# Progetto_PAWM

Front end implementato con Angular e backend con Firebase (reatime db). 

Front end, sezioni: 
- login e registrazione: chiamate al server firebase, login gestito con username e password, come risposta il server restituisce un jwt token. 
- profilo: informazioni sull'utente che ha eseguito il login
- bar e cucina: sezioni utilizzate dagli utenti che lavorano al bar o in cucina e possono gestire tutte le comande che arrivano. 
- tavoli: sezione che permette ai camerieri o a chi sta all'accoglienza di gestire i tavoli e le comande.
- menu: sezione per gestire gli elementi del menu. 

Dopo aver eseguito il login, le informazioni dell'utente vengono salvate nel local storage del browser. 
Ogni volta che viene fatta una richiesta http al server entra in gioco un interceptor che aggiunge il token per pemettere di autorizzare le chiamate al server. 

Lato server: 
Realtime database gestisce i dati attraverso file JSON. autenticare le chiamate è presente una console dove vanno indicate le regole di acesso al db.
Nel nostro caso l'accesso alle tabelle riferite ai tavoli, elementi del menu e comande è consentito a tutti gli utenti autenticati, mentre quello alla tabella riferita agli admin è riservato solo agli admin

---------------------------------------------------------------------------

Front-end implemented using Angular, with a Firebase (Realtime Database) back-end.

Front-end sections:
- Login and registration: Calls are made to the Firebase server; login is handled via username and password, with the server returning a JWT token upon successful authentication.
- Profile: Displays information about the logged-in user.
- Bar and Kitchen: Sections used by staff working in the bar or kitchen to manage incoming orders.
- Tables: A section that allows waitstaff or reception/host staff to manage tables and orders.
- Menu: A section for managing menu items.

After logging in, user information is stored in the browser's local storage.
Whenever an HTTP request is made to the server, an interceptor automatically adds the token to authorize the request.

Server-side:
The Realtime Database manages data using JSON-formatted structures. Access rules for the database are defined via a dedicated console.
In our implementation, access to the tables for tables, menu items, and orders is granted to all authenticated users, while access to the table reserved for administrators is restricted to admin users only.
