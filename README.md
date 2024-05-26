# Oklid
Kodluyoruz ödev
import math


points = [(-3, 0), (0, 0), (0, 4)]


def euclideanDistance(point1, point2):
    return math.sqrt((point2[0] - point1[0]) ** 2 + (point2[1] - point1[1]) ** 2)


distances = []
names = ['a', 'b', 'c']
distance_dict = {}

index = 0
for i in range(len(points)):
    for j in range(i + 1, len(points)):
        distance = euclideanDistance(points[i], points[j])
        distance_name = names[index]
        distance_dict[distance_name] = distance
        print(f"{distance_name} arasındaki mesafe: {distance}")
        distances.append(distance)
        index += 1


if distances:  # Mesafeler listesi boş olmadığından emin ol
    min_distance = min(distances)
    min_distance_name = [name for name, dist in distance_dict.items() if dist == min_distance][0]
    print(f"Minimum mesafe ({min_distance_name}): {min_distance}")
else:
    print("Hesaplanacak mesafe bulunamadı")
