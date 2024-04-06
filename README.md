import pygame
import sys

# Initialiser Pygame
pygame.init()

# Définir les couleurs
BLANC = (255, 255, 255)
NOIR = (0, 0, 0)

# Définir les dimensions de la fenêtre
largeur = 800
hauteur = 600

# Créer la fenêtre
fenetre = pygame.display.set_mode((largeur, hauteur))
pygame.display.set_caption("Jeu en 2D")

# Position initiale du carré
x = largeur // 2
y = hauteur // 2

# Taille du carré
taille = 50

# Vitesse de déplacement du carré
vitesse = 5

# Boucle principale du jeu
while True:
    fenetre.fill(BLANC)  # Remplir la fenêtre avec la couleur blanche

    # Gérer les événements
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Gérer les entrées du clavier pour déplacer le carré
    touches = pygame.key.get_pressed()
    if touches[pygame.K_LEFT]:
        x -= vitesse
    if touches[pygame.K_RIGHT]:
        x += vitesse
    if touches[pygame.K_UP]:
        y -= vitesse
    if touches[pygame.K_DOWN]:
        y += vitesse

    # Dessiner le carré
    pygame.draw.rect(fenetre, NOIR, (x, y, taille, taille))

    # Mettre à jour l'affichage
    pygame.display.flip()

 
