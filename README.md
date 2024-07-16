#!/bin/bash

# Função para exibir o banner com o coelho em ASCII
function show_banner() {
    echo "----------------------------------------------"
    echo "          /\_/\  ( Coder Bunny)"
    echo "         ( o.o )"
    echo "          > ^ <"
    echo "----------------------------------------------"
    echo "Bunny Web Checker"
    echo "----------------------------------------------"
}

# Função para fazer consultas HTTP aos sites selecionados
function check_sites() {
    declare -a sites=(
        "https://www.example.com"
        "https://www.google.com"
        "https://www.github.com"
    )

    for site in "${sites[@]}"
    do
        echo "Checking $site ..."
        status_code=$(curl -o /dev/null -s -w "%{http_code}\n" $site)
        echo "Status Code: $status_code"
        echo "----------------------------------------------"
    done
}

# Exibir o banner
show_banner

# Realizar as consultas aos sites
check_sites
