package puff;

import org.bukkit.Bukkit;
import org.bukkit.ChatColor;
import org.bukkit.Material;
import org.bukkit.command.Command;
import org.bukkit.command.CommandSender;
import org.bukkit.entity.Player;
import org.bukkit.event.EventHandler;
import org.bukkit.event.Listener;

import org.bukkit.event.inventory.InventoryClickEvent;

import org.bukkit.inventory.Inventory;
import org.bukkit.inventory.ItemStack;
import org.bukkit.inventory.meta.ItemMeta;
import org.bukkit.plugin.java.JavaPlugin;

import java.util.ArrayList;
import java.util.List;




public class main extends JavaPlugin implements Listener {

    @Override
    public void onEnable() {

        getServer().getPluginManager().registerEvents(this, this);
        getServer().getPluginManager().registerEvents(new RulesClick(), this);
        getCommand("donate").setExecutor(this::onCommand);
        getCommand("Rules").setExecutor(new Rules());

    }

    @Override
    public void onDisable() {


    }


    @Override
    public boolean onCommand(CommandSender sender, Command cmd, String label, String[] args) {
        if (cmd.getName().equalsIgnoreCase("donate")) {
            if (sender instanceof Player) {
                Player player = (Player) sender;
                openDonateMenu(player);
            } else {
                sender.sendMessage(ChatColor.RED + "ошибка, консоль? игрок?");
            }
            return true;
        }
        return false;
    }


    public void openDonateMenu(Player player) {
        Inventory DonateMenu = Bukkit.createInventory(null, 54, ChatColor.BOLD + "" + ChatColor.DARK_AQUA + "Donate");


        ItemStack item1 = new ItemStack(Material.DIAMOND);
        ItemMeta item1Meta = item1.getItemMeta();
        item1Meta.setDisplayName(ChatColor.DARK_BLUE + "Amarok");
        item1.setItemMeta(item1Meta);
        List<String> lore1 = new ArrayList();
        lore1.add(ChatColor.DARK_GREEN + "" + ChatColor.BOLD + "this mythical beast gives such advantages as: ");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "15% discount on all gadgets/mystery boxes. ");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "3 free Mystery Boxes for free!");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Match wins will gain you 6$ in-game instead of 5$ in-game.");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Unique prefix in a tab.");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Role in Discord.");
        lore1.add(ChatColor.GREEN + "" + ChatColor.BOLD + "/sit + /afk in the lobby.");
        lore1.add(ChatColor.AQUA + "" + ChatColor.BOLD + "price: $2 ");
        item1Meta.setLore(lore1);
        item1.setItemMeta(item1Meta);

        ItemStack item2 = new ItemStack(Material.APPLE);
        ItemMeta item2Meta = item2.getItemMeta();
        item2Meta.setDisplayName(ChatColor.BLUE + "Krampus");
        List<String> lore2 = new ArrayList();
        lore2.add(ChatColor.DARK_GREEN + "" + ChatColor.BOLD + "this mythical beast gives such advantages as: ");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "All the features of Amarok. ");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "40% discount on all gadgets/mystery boxes. ");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Access to VIP and MVP chat (in the future).");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Unique prefix in a tab.");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Match wins will gain you 8$ in-game instead of 5$ in-game.");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Ability to change nickname!");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Sneak-peak for future updates.");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Exclusive commands(detailed on the site)");
        lore2.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Role in Discord.");
        lore2.add(ChatColor.AQUA + "" + ChatColor.BOLD + "price: $5 ");
        item2Meta.setLore(lore2);
        item2.setItemMeta(item2Meta);

        ItemStack item11 = new ItemStack(Material.ICE);
        ItemMeta item11Meta = item11.getItemMeta();
        item11Meta.setDisplayName(ChatColor.AQUA + "" + ChatColor.BOLD+"Yeti");
        List<String> lore11 = new ArrayList();
        lore11.add(ChatColor.DARK_GREEN + "" + ChatColor.BOLD + "this mythical beast gives such advantages as: ");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "All the features of Amarok. ");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "60% discount on all gadgets/mystery boxes. ");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Access to VIP and MVP chat (in the future).");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Unique prefix in a tab.");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Match wins will gain you 8$ in-game instead of 10$ in-game.");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Ability to change nickname!");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "Exclusive commands(detailed on the site)");
        lore11.add(ChatColor.GREEN + "" + ChatColor.BOLD + "prefix in the tab");
        lore11.add(ChatColor.AQUA + "" + ChatColor.BOLD + "price: $10 ");
        item11Meta.setLore(lore11);
        item11.setItemMeta(item11Meta);






        ItemStack item4 = new ItemStack(Material.ENDER_PEARL);
        ItemMeta item4Meta = item4.getItemMeta();
        item4Meta.setDisplayName(ChatColor.GREEN + "" + ChatColor.BOLD + "Custom rank");
        List<String> lore4 = new ArrayList();
        lore4.add(ChatColor.DARK_GREEN + "" + ChatColor.BOLD + "all rights are the same as the yeti, but the player can change his rank  ");
        lore4.add(ChatColor.GREEN + "" + ChatColor.BOLD + "custom rank, unlike other donation ranks, does not disappear ");
        lore4.add(ChatColor.AQUA + "" + ChatColor.BOLD + "price: $19.99 ");
        item4Meta.setLore(lore4);
        item4.setItemMeta(item4Meta);



        ItemStack item12 = new ItemStack(Material.REDSTONE);
        ItemMeta item12Meta = item12.getItemMeta();
        item12Meta.setDisplayName(ChatColor.RED + "" + ChatColor.BOLD + "Admin");
        item12.setItemMeta(item12Meta);



        ItemStack item6 = new ItemStack(Material.GOLD_INGOT);
        ItemMeta item6Meta = item6.getItemMeta();
        item6Meta.setDisplayName(ChatColor.YELLOW + "" + ChatColor.BOLD + "in-game coins");
        List<String> lore6 = new ArrayList();
        lore6.add(ChatColor.GOLD + "" + ChatColor.BOLD + "GOLD");
        lore6.add(ChatColor.GOLD + "" + ChatColor.BOLD + "GOLD");
        lore6.add(ChatColor.GOLD + "" + ChatColor.BOLD + "need more gold");
        item6Meta.setLore(lore6);
        item6.setItemMeta(item6Meta);


        DonateMenu.setItem(11, item1);
        DonateMenu.setItem(13, item2);
        DonateMenu.setItem(29, item4);
        DonateMenu.setItem(31, item6);
        DonateMenu.setItem(33, item12);
        DonateMenu.setItem(15,item11);

        player.openInventory(DonateMenu);
    }

    @EventHandler
    public void onInventoryClick(InventoryClickEvent event) {
        Player player = (Player) event.getWhoClicked();
        Inventory inventory = event.getInventory();
        ItemStack clicked = event.getCurrentItem();
        if (inventory.getName().equals(ChatColor.BOLD + "" + ChatColor.DARK_AQUA + "Donate")) {
            if (clicked.getType() == Material.DIAMOND) {
                player.closeInventory();
                player.sendMessage(ChatColor.GOLD + "https://snowcentral.tebex.io/package/5486385");
                player.sendMessage(ChatColor.GREEN + "" + ChatColor.BOLD + "click on the ling to go to the store");
                event.setCancelled(true);
            }
            // крампус
            if (clicked.getType() == Material.APPLE) {
                player.closeInventory();
                player.sendMessage(ChatColor.GOLD + "https://snowcentral.tebex.io/package/5486382");
                player.sendMessage(ChatColor.GREEN + "" + ChatColor.BOLD + "click on the ling to go to the store");
                event.setCancelled(true);
            }
            // йети
            if (clicked.getType() == Material.ICE) {
                player.closeInventory();
                player.sendMessage(ChatColor.GOLD + "https://snowcentral.tebex.io/package/5483498");
                player.sendMessage(ChatColor.GREEN + "" + ChatColor.BOLD + "click on the ling to go to the store");
                event.setCancelled(true);
            }
            // модератор
            if (clicked.getType() == Material.REDSTONE) {
                player.closeInventory();
                player.sendMessage(ChatColor.MAGIC + "@ItzNa3aR1758");
                player.sendMessage(ChatColor.DARK_AQUA + "oh, what?");
                event.setCancelled(true);
            }
            //монеты
            if (clicked.getType() == Material.GOLD_INGOT) {
                player.closeInventory();
                player.sendMessage(ChatColor.GOLD + "https://snowcentral.tebex.io/category/coins-and-more");
                player.sendMessage(ChatColor.GREEN + "" + ChatColor.BOLD + "click on the ling to go to the store");
                event.setCancelled(true);
            }
            //кастом
            if (clicked.getType() == Material.ENDER_PEARL) {
                player.closeInventory();
                player.sendMessage(ChatColor.GOLD + "https://snowcentral.tebex.io/package/5486374");
                player.sendMessage(ChatColor.GREEN + "" + ChatColor.BOLD + "click on the ling to go to the store");
                event.setCancelled(true);
            }

            }
        }


    }
