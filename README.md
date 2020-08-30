# WP-MyPageTpl

function d0 ($templates) {
    $templates['my-custom-template.php'] = 'My Template';
    return $templates;
    }
add_filter ('theme_page_templates', 'd0');

function d1 ($template) {

    $post = get_post(); 
    $page_template = get_post_meta( $post->ID, '_wp_page_template', true ); 
    echo $page_template;
    exit();

    }
add_filter ('page_template', 'd1');
