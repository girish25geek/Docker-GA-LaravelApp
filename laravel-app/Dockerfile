FROM php:8.2-apache

# Enable rewrite module for Laravel routing
RUN a2enmod rewrite

# Set working dir
WORKDIR /var/www

# Copy full Laravel app
COPY . .

# Point Apache to Laravel's public folder
RUN rm -rf /var/www/html && ln -s /var/www/public /var/www/html

# Set permissions
RUN chown -R www-data:www-data /var/www \
    && chmod -R 755 /var/www

EXPOSE 80

CMD ["apache2-foreground"]
