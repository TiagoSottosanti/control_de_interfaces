//Actividad 2//
#include <stdio.h>
#include "pico/stdlib.h"

 @brief
 
int main(void) {
	stdio_init_all();
	sleep_ms(1000);

 Inicializacion de GPIO con gpio_init()
    gpio_init(6);
    gpio_init(20);
    gpio_init(7);
    gpio_init(21);
    gpio_init(8);
    gpio_init(22);
    gpio_set_dir(20, false);
    gpio_set_dir(6, true);
    gpio_set_dir(21, false);
    gpio_set_dir(7, true);
    gpio_set_dir(22, false);
    gpio_set_dir(8, true);


	
while (true) {
 Resolver logica para GPIO20 -> GPIO6
        if (gpio_get(20) == 0)
        {
            gpio_put(6, 1);
        }
        else
        {
            gpio_put(6, 0);
        }
		// Resolver logica para GPIO21 -> GPIO7
        if (gpio_get(21)==0)
        {
            if (gpio_get(7)==0)
            {
                /* code */
                gpio_put(7, 0);
            }
            else {
                gpio_put(7, 1);
            }
            
        }
 Resolver logica para GPIO22 -> GPIO8
        while (gpio_get(22)==0)
        {
            gpio_put(8, 1);
            delay(500);
            gpio_put(8, 0);
            delay(500);
        }
}
	return 0;
}
