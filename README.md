### Flask SQLAlchemy

```
    python3 -V
    sudo apt install python3-venv
    python3 -m venv venv
    source venv/bin/activate

    pip install Flask
    pip install flask-sqlalchemy

    deactivate

    >>> db.create_all()
    >>> from one_two_many import Pet, Person
    >>> anthony = Person(name='Antony')
    >>> db.session.add(anthony)
    >>> db.session.commit()
    >>> mishelle = Person(name='Mishelle')
    >>> db.session.add(mishelle)
    >>> db.session.commit()
    >>> spot = Pet(name='Spot', owner=anthony)
    >>> db.session.add(spot)
    >>> db.session.commit()
    >>> brian = Pet(name='Brian', owner=mishelle)
    >>> db.session.add(brian)
    >>> db.session.commit()

    >>> cliford = Pet(name='Cliford', owner=anthony)
    >>> db.session.add(cliford)
    >>> db.session.commit()
    >>> anthony
    <Person 1>
    >>> anthony.pets
    [<Pet 1>, <Pet 3>]
    >>> anthony.pets[1]
    <Pet 3>
    >>> mishelle = Person.query.filter_by(name='Mishelle').first()
    >>> mishelle
    <Person 2>
    >>> mishelle.pets
    [<Pet 2>]
```