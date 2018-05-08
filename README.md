# Ejemplos de operaciones basicas en MongoDB

//1.-Obtener todos los documentos
db.Movies.find();
//2.-Obtener documentos con writer igual a "Quentin Tarantino"
db.Movies.find({writer:'Quentin Tarantino'})
//3.-Obtener documentos con actors que incluyan a "Brad Pitt"
db.Movies.find({actors:'Brad Pitt'})
//4.-Obtener documentos con franchise igual a "The Hobbit"
db.Movies.find({franchise:'The Hobbit'})
//5.-Obtener todas las películas de los 90s.
db.Movies.find({$and:[{year:{$gte:"1990"}},{year:{$lte:"1999"}}]})
//6.-Obtener las películas estrenadas entre el año 2000 y 2010.
db.Movies.find({$and:[{year:{$gte:"2000"}},{year:{$lte:"2010"}}]})

// Actualizar Documentos
//1 y 2
db.Movies.update({_id:ObjectId("5af1dc4b66e7e379b946a90c")},
    {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
//3
db.Movies.update({title:"Pulp Fiction"},{$push:{actors:"Samuel L. Jackson"}})

//Eliminar
db.Movies.remove({title:"Pee Wee Herman's Big Adventure"})
db.Movies.remove({title:"Avatar"})


