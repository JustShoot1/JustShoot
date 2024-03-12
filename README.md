package Código4;
import robocode.*;

public class JustShoot extends AdvancedRobot {
    public void run() {
        while (true) {
            // Implemente sua lógica de movimento aqui
            ahead(100);
            turnRight(90);
        }
    }

    public void onScannedRobot(ScannedRobotEvent e) {
        // Implemente sua lógica de combate aqui
        double distancia = e.getDistance();
        if (distancia < 200) {
            fire(3); // Ajuste a potência do tiro conforme a distância
        } else if (distancia < 500) {
            fire(2);
        } else {
            fire(1);
        }
    }

    public void onHitByBullet(HitByBulletEvent e) {
        // Implemente sua reação quando for atingido por uma bala
        back(20);
    }

    public void onHitWall(HitWallEvent e) {
        // Implemente sua reação quando colidir com uma parede
        turnRight(90);
        ahead(50);
    }
}
