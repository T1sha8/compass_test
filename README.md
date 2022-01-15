def direction(facing, turn):
    # your smart code here
    directions = {
        "N": 0,
        "NE": 45,
        "E": 90,
        "SE": 135,
        "S": 180,
        "SW": 225,
        "W": 270,
        "NW": 315,
    }

    # Cycle to search for a given direction in the dictionary and add turns to turn
    for k, v in directions.items():
        if facing == k:
            degrees = v + turn
            while degrees < 0:  # If the degrees are less than 0, then we get 360 degrees
                degrees += 360
            while degrees > 360:  # If the degree is greater than 360, then subtract 360 degrees
                degrees -= 360

    # Cycle to search for a course after a turn
    for k, v in directions.items():
        if degrees == v:
            return k
        # N = 0 and 360
        if degrees == 360:
            return "N"
